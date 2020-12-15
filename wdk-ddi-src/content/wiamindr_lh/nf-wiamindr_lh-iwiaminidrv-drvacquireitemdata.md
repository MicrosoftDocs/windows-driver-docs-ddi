---
UID: NF:wiamindr_lh.IWiaMiniDrv.drvAcquireItemData
title: IWiaMiniDrv::drvAcquireItemData (wiamindr_lh.h)
description: The IWiaMiniDrv::drvAcquireItemData method is called by the WIA service to transfer data from the device to an application.
old-location: image\iwiaminidrv_drvacquireitemdata.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["IWiaMiniDrv::drvAcquireItemData"]
ms.keywords: IWiaMiniDrv interface [Imaging Devices],drvAcquireItemData method, IWiaMiniDrv.drvAcquireItemData, IWiaMiniDrv::drvAcquireItemData, MiniDrv_fb4ad9e4-6648-4038-9b72-4e521d4dd5f2.xml, drvAcquireItemData, drvAcquireItemData method [Imaging Devices], drvAcquireItemData method [Imaging Devices],IWiaMiniDrv interface, image.iwiaminidrv_drvacquireitemdata, wiamindr_lh/IWiaMiniDrv::drvAcquireItemData
req.header: wiamindr_lh.h
req.include-header: Wiamindr.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IWiaMiniDrv::drvAcquireItemData
 - wiamindr_lh/IWiaMiniDrv::drvAcquireItemData
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - wiamindr_lh.h
api_name:
 - IWiaMiniDrv.drvAcquireItemData
---

# IWiaMiniDrv::drvAcquireItemData


## -description

The **IWiaMiniDrv::drvAcquireItemData** method is called by the WIA service to transfer data from the device to an application.

## -parameters

### -param __MIDL__IWiaMiniDrv0009

lFlags [in]

- Is currently unused.

### -param __MIDL__IWiaMiniDrv0010

pWiasContext [in]

- Pointer to a WIA item context.

### -param __MIDL__IWiaMiniDrv0011

plDevErrVal [out]

- Points to a memory location that will receive a status code for this method. If this method returns S_OK, the value stored will be zero. Otherwise, a minidriver-specific error code will be stored at the location pointed to by this parameter.

### -param __MIDL__IWiaMiniDrv0012

pmdtc [in, out]

- Points to a [MINIDRV_TRANSFER_CONTEXT](./ns-wiamindr_lh-_minidrv_transfer_context.md) structure containing the device transfer context. The MINIDRV_TRANSFER_CONTEXT structure contains parameters that pertain to the data to be transferred.

#### - lFlags [in]

Is currently unused.

#### - pWiasContext [in]

Pointer to a WIA item context.

#### - plDevErrVal [out]

Points to a memory location that will receive a status code for this method. If this method returns S_OK, the value stored will be zero. Otherwise, a minidriver-specific error code will be stored at the location pointed to by this parameter.

#### - pmdtc [in, out]

Points to a [MINIDRV_TRANSFER_CONTEXT](./ns-wiamindr_lh-_minidrv_transfer_context.md) structure containing the device transfer context. The MINIDRV_TRANSFER_CONTEXT structure contains parameters that pertain to the data to be transferred.

## -returns

On success, the method should return S_OK and clear the device error value pointed to by **plDevErrVal**. If the transfer was canceled, the method should return S_FALSE. If the method fails, it should return a standard COM error code and fill in a minidriver-specific error code value in the memory pointed to by **plDevErrVal**. The **Remarks** section has additional return-value information that applies to ADF scanning.

## -remarks

There are two main types of transfer: memory-based, and file-based. The WIA service indicates which type is to be performed by the setting of *pmdtc*-->**tymed**, which will be TYMED_CALLBACK or TYMED_MULTIPAGE_CALLBACK for memory-based transfers, and TYMED_FILE or TYMED_MULTIPAGE_FILE for file transfers. For more information about these constants, see [WIA_IPA_TYMED](/windows-hardware/drivers/image/wia-ipa-tymed).

- For memory-based transfers, a buffer may or may not have already been allocated, as indicated by the value in *pmdtc*-->**bClassDrvAllocBuf**. The WIA service can pass up to two buffers to the minidriver, but typically passes only one. The number of buffers is specified by the value in *pmdtc*-->**lNumBuffers**. If memory for the buffer is not already allocated, the minidriver should allocate it using any of the usual means, such as [**CoTaskMemAlloc**](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemalloc), or **new**. If the minidriver allocates a buffer, it also has the responsibility of freeing the buffer.

- For file transfers, the minidriver should first write the data to the buffer passed in the WIA service's call to this method, and then call [wiasWritePageBufToFile](../wiamdef/nf-wiamdef-wiaswritepagebuftofile.md) to write the buffer data to the file involved. The minidriver should not attempt to use the file handle specified in **pmdtc**-->**hFile** to write the data to the file.

Periodically, the minidriver should call the [IWiaMiniDrvCallBack::MiniDrvCallback](./nf-wiamindr_lh-iwiaminidrvcallback-minidrvcallback.md) method in the COM interface point to by *pdmtc*-->**pIWiaMiniDrvCallBack** to update the status of the transfer. For memory-based transfers, this function is used to pass the data back to the application. How often this function should be called is left to the minidriver, but it should be called about ten times, or roughly once per second during the transfer, whichever is more often.

Other transfer parameters that the WIA service provides include the following:

- **pmdtc**-->**guidFormatID** - the data format

- **pmdtc**-->**lCompression** - the type of compression used

A potential problem for ADF-equipped scanners is running out of paper during a scan operation. The HRESULT that your implementation of **IWiaMiniDrv::drvAcquireItemData** returns depends on the current setting of the scanner's WIA_DPS_PAGES property, and whether all pages were properly scanned. Use the following rules to guide you in determining the appropriate HRESULT to return in this method.

| Scenario | HRESULT value |
| --- | --- |
| The WIA_DPS_PAGES property was set to 0, and the scanner emptied its ADF with no errors.<br>The WIA_DPS_PAGES property was set to N (where N > 0), and the scanner processed N pages with no errors. | S_OK |
| The WIA_DPS_PAGES property was set to N, and the scanner processed at least one page but ran out of paper before processing all N pages. | WIA_STATUS_END_OF_MEDIA |
| The scanner has unexpectedly detected multiple page feed, stopped scanning, and has set the [WIA_DPS_DOCUMENT_HANDLING_STATUS](/windows-hardware/drivers/image/wia-dps-document-handling-status) to MULTIPLE_FEED. | WIA_ERROR_MULTI_FEED |
| The scanner ran out of paper on the first scan, regardless of the setting of the WIA_DPS_PAGES property.<br>A paper jam or other error occurred during the scan operation. | Other error code |

## -see-also

[IWiaMiniDrv](./nn-wiamindr_lh-iwiaminidrv.md)

[IWiaMiniDrv::drvGetDeviceErrorStr](./nf-wiamindr_lh-iwiaminidrv-drvgetdeviceerrorstr.md)

[MINIDRV_TRANSFER_CONTEXT](./ns-wiamindr_lh-_minidrv_transfer_context.md)

[wiasGetImageInformation](../wiamdef/nf-wiamdef-wiasgetimageinformation.md)

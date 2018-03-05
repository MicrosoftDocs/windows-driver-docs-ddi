---
UID: NF:wiamindr_lh.IWiaMiniDrv.drvGetWiaFormatInfo
title: IWiaMiniDrv::drvGetWiaFormatInfo method
author: windows-driver-content
description: The IWiaMiniDrv::drvGetWiaFormatInfo method finds the image formats and media types that the WIA hardware device supports.
old-location: image\iwiaminidrv_drvgetwiaformatinfo.htm
old-project: image
ms.assetid: f0b7d982-735f-489c-b9f8-81a287f6722a
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IWiaMiniDrv, IWiaMiniDrv interface [Imaging Devices], drvGetWiaFormatInfo method, IWiaMiniDrv::drvGetWiaFormatInfo, MiniDrv_6c0cb527-6884-4b7d-a7cc-0e09c1774b7f.xml, drvGetWiaFormatInfo method [Imaging Devices], drvGetWiaFormatInfo method [Imaging Devices], IWiaMiniDrv interface, drvGetWiaFormatInfo,IWiaMiniDrv.drvGetWiaFormatInfo, image.iwiaminidrv_drvgetwiaformatinfo, wiamindr_lh/IWiaMiniDrv::drvGetWiaFormatInfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wiamindr_lh.h
req.include-header: Wiamindr.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Me and in Windows XP and later.
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
req.lib: wiamindr_lh.h
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	wiamindr_lh.h
api_name:
-	IWiaMiniDrv.drvGetWiaFormatInfo
product: Windows
targetos: Windows
req.typenames: SCANWINDOW, *PSCANWINDOW
req.product: Windows 10 or later.
---

# IWiaMiniDrv::drvGetWiaFormatInfo method


## -description


The <b>IWiaMiniDrv::drvGetWiaFormatInfo</b> method finds the image formats and media types that the WIA hardware device supports.


## -syntax


````
HRESULT drvGetWiaFormatInfo(
  [in]            BYTE            *pWiasContext,
  [in]            LONG            lFlags,
  [out]           LONG            *pcelt,
  [out, optional] WIA_FORMAT_INFO **ppwfi,
  [out]           LONG            *plDevErrVal
);
````


## -parameters




### -param __MIDL__IWiaMiniDrv0059




### -param __MIDL__IWiaMiniDrv0060




### -param __MIDL__IWiaMiniDrv0061




### -param __MIDL__IWiaMiniDrv0062




### -param __MIDL__IWiaMiniDrv0063






#### - pWiasContext [in]

Pointer to a WIA item context.


#### - lFlags [in]

Is currently unused. 


#### - pcelt [out]

Points to a memory location that will receive the number of items in the array pointed to by <i>ppwfi</i>.


#### - ppwfi [out, optional]

Points to a memory location that will receive the address of the first element of an array of WIA_FORMAT_INFO structures (described in the Microsoft Windows SDK documentation).


#### - plDevErrVal [out]

Points to a memory location that will receive a status code for this method. If this method returns S_OK, the value stored will be zero. Otherwise, a minidriver-specific error code will be stored at the location pointed to by this parameter.


## -returns



On success, the method should return S_OK and clear the device error value pointed to by <i>plDevErrVal</i>. If this method is called for items that do not contain any data, it should return E_INVALIDARG. If the method fails, it should return a standard COM error code and place a minidriver-specific error code value in the memory pointed to by <i>plDevErrVal</i>. 

The value pointed to by <i>plDevErrVal</i> can be converted to a string by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543982">IWiaMiniDrv::drvGetDeviceErrorStr</a>.




## -remarks



This method creates an array of WIA_FORMAT_INFO structures (defined in the Windows SDK documentation) that describe the media types and image formats that the WIA hardware device supports. For each element in the array, the media type can be one of TYMED_CALLBACK, TYMED_MULTIPAGE_CALLBACK, TYMED_FILE, or TYMED_MULTIPAGE_FILE (constants defined in the Windows SDK documentation). Typical values for the image format include WiaImgFmt_JPEG, and WiaImgFmt_BMP (also defined in the Windows SDK documentation), among others. 

The minidriver can define a global array to hold the WIA_FORMAT_INFO structures, or it can allocate memory for the array. The WIA service will not free the allocated memory, so the minidriver should store a pointer to that memory in the driver item context. The minidriver can then free this memory in a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543972">IWiaMiniDrv::drvFreeDrvItemContext</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543972">IWiaMiniDrv::drvFreeDrvItemContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543982">IWiaMiniDrv::drvGetDeviceErrorStr</a>



<a href="..\wiamindr_lh\nn-wiamindr_lh-iwiaminidrv.md">IWiaMiniDrv</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IWiaMiniDrv::drvGetWiaFormatInfo method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


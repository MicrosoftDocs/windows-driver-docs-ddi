---
UID: NF:wudfusb.IWDFUsbTargetDevice.FormatRequestForControlTransfer
title: IWDFUsbTargetDevice::FormatRequestForControlTransfer (wudfusb.h)
description: The FormatRequestForControlTransfer method formats an I/O request object for a USB control transfer.
old-location: wdf\iwdfusbtargetdevice_formatrequestforcontroltransfer.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["IWDFUsbTargetDevice::FormatRequestForControlTransfer"]
ms.keywords: FormatRequestForControlTransfer, FormatRequestForControlTransfer method, FormatRequestForControlTransfer method,IWDFUsbTargetDevice interface, IWDFUsbTargetDevice interface,FormatRequestForControlTransfer method, IWDFUsbTargetDevice.FormatRequestForControlTransfer, IWDFUsbTargetDevice::FormatRequestForControlTransfer, UMDFUSBref_01a86f28-7a72-4d7b-a2f5-1e254fb26192.xml, umdf.iwdfusbtargetdevice_formatrequestforcontroltransfer, wdf.iwdfusbtargetdevice_formatrequestforcontroltransfer, wudfusb/IWDFUsbTargetDevice::FormatRequestForControlTransfer
req.header: wudfusb.h
req.include-header: Wudfusb.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDFUsbTargetDevice::FormatRequestForControlTransfer
 - wudfusb/IWDFUsbTargetDevice::FormatRequestForControlTransfer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFUsbTargetDevice::FormatRequestForControlTransfer
---

# IWDFUsbTargetDevice::FormatRequestForControlTransfer


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>FormatRequestForControlTransfer</b> method formats an I/O request object for a USB control transfer.

## -parameters

### -param pRequest 

[in]
A pointer to the <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequest">IWDFIoRequest</a> interface for the request object to format.

### -param SetupPacket 

[in]
A pointer to a <a href="/windows/win32/api/winusb/ns-winusb-winusb_setup_packet">WINUSB_SETUP_PACKET</a> for the control transfer.

### -param pMemory 

[in, optional]
A pointer to the <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfmemory">IWDFMemory</a> interface that is used to access the buffer that is used for the control transfer. This parameter is optional.

### -param TransferOffset 

[in, optional]
A pointer to a <a href="/windows-hardware/drivers/ddi/wudfddi_types/ns-wudfddi_types-_wdfmemory_offset">WDFMEMORY_OFFSET</a> structure that describes the memory offset that is used for the control transfer. This parameter is optional.

## -returns

<b>FormatRequestForControlTransfer</b> returns one of the following values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK </b></dt>
</dl>
</td>
<td width="60%">

<a href="/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbtargetdevice-formatrequestforcontroltransfer">FormatRequestForControlTransfer</a> successfully formatted an I/O request object. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY </b></dt>
</dl>
</td>
<td width="60%">

<a href="/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbtargetdevice-formatrequestforcontroltransfer">FormatRequestForControlTransfer</a> encountered an allocation failure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG </b></dt>
</dl>
</td>
<td width="60%">
The memory offset that the <i>TransferOffset</i> parameter specified was invalid.

</td>
</tr>
</table>

## -remarks

After a UMDF driver calls <b>FormatRequestForControlTransfer</b> to format an I/O request for a control transfer operation, the framework can subsequently send the request to the I/O target.


#### Examples

The following code example is taken from the <a href="/samples/browse/?redirectedfrom=MSDN-samples">wdf_osrfx2_lab</a> sample in the WDK.


```
    WINUSB_CONTROL_SETUP_PACKET setupPacket;

    ULONG bytesTransferred;

    HRESULT hr = S_OK;

    //
    // Setup the control packet.
    //

    WINUSB_CONTROL_SETUP_PACKET_INIT( &setupPacket,
                                      BmRequestHostToDevice,
                                      BmRequestToDevice,
                                      USBFX2LK_SET_BARGRAPH_DISPLAY,
                                      0,
                                      0 );

    //
    // Issue the request to WinUsb.
    //

    hr = SendControlTransferSynchronously(
                &(setupPacket.WinUsb),
                (PUCHAR) BarGraphState,
                sizeof(BAR_GRAPH_STATE),
                &bytesTransferred
                );
...

HRESULT
CMyDevice::SendControlTransferSynchronously(
    _In_ PWINUSB_SETUP_PACKET SetupPacket,
    _Inout_updates_(BufferLength) PBYTE Buffer,
    _In_ ULONG BufferLength,
    _Out_ PULONG LengthTransferred
    )
{
    HRESULT hr = S_OK;
    IWDFIoRequest *pWdfRequest = NULL;
    IWDFDriver * FxDriver = NULL;
    IWDFMemory * FxMemory = NULL; 
    IWDFRequestCompletionParams * FxComplParams = NULL;
    IWDFUsbRequestCompletionParams * FxUsbComplParams = NULL;

    *LengthTransferred = 0;
    
    hr = m_FxDevice->CreateRequest( NULL, //pCallbackInterface
                                    NULL, //pParentObject
                                    &pWdfRequest);

    if (SUCCEEDED(hr))
    {
        m_FxDevice->GetDriver(&FxDriver);

        hr = FxDriver->CreatePreallocatedWdfMemory( Buffer,
                                                    BufferLength,
                                                    NULL, //pCallbackInterface
                                                    pWdfRequest, //pParetObject
                                                    &FxMemory );
    }

    if (SUCCEEDED(hr))
    {
        hr = m_pIUsbTargetDevice->FormatRequestForControlTransfer( pWdfRequest,
                                                                   SetupPacket,
                                                                   FxMemory,
                                                                   NULL); //TransferOffset
    }                                                          
      

```

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequest">IWDFIoRequest</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfmemory">IWDFMemory</a>



<a href="/windows-hardware/drivers/ddi/wudfusb/nn-wudfusb-iwdfusbtargetdevice">IWDFUsbTargetDevice</a>



<a href="/windows-hardware/drivers/ddi/wudfddi_types/ns-wudfddi_types-_wdfmemory_offset">WDFMEMORY_OFFSET</a>


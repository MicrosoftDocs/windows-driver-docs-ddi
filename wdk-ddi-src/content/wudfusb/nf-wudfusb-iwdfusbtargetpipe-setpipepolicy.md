---
UID: NF:wudfusb.IWDFUsbTargetPipe.SetPipePolicy
title: IWDFUsbTargetPipe::SetPipePolicy (wudfusb.h)
description: The SetPipePolicy method sets the WinUsb pipe policy.
old-location: wdf\iwdfusbtargetpipe_setpipepolicy.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["IWDFUsbTargetPipe::SetPipePolicy"]
ms.keywords: IWDFUsbTargetPipe interface,SetPipePolicy method, IWDFUsbTargetPipe.SetPipePolicy, IWDFUsbTargetPipe::SetPipePolicy, SetPipePolicy, SetPipePolicy method, SetPipePolicy method,IWDFUsbTargetPipe interface, UMDFUSBref_ab486cfe-19aa-440c-a017-e956aa4d2bb1.xml, umdf.iwdfusbtargetpipe_setpipepolicy, wdf.iwdfusbtargetpipe_setpipepolicy, wudfusb/IWDFUsbTargetPipe::SetPipePolicy
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
 - IWDFUsbTargetPipe::SetPipePolicy
 - wudfusb/IWDFUsbTargetPipe::SetPipePolicy
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFUsbTargetPipe.SetPipePolicy
---

# IWDFUsbTargetPipe::SetPipePolicy


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>SetPipePolicy</b> method sets the WinUsb pipe policy.

## -parameters

### -param PolicyType 

[in]
The type of WinUsb pipe policy that the UMDF driver sets.

### -param ValueLength 

[in]
The size, in bytes, of the buffer that <b>SetPipePolicy</b> supplies for <i>Value</i>.

### -param Value 

[in]
A pointer to the buffer that contains the WinUsb pipe policy.

## -returns

<b>SetPipePolicy</b> returns one of the following values: 

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

<a href="/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbtargetpipe-setpipepolicy">SetPipePolicy</a> successfully set the WinUsb pipe policy. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY </b></dt>
</dl>
</td>
<td width="60%">

<a href="/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbtargetpipe-setpipepolicy">SetPipePolicy</a> encountered an allocation failure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>An error code that is defined in Winerror.h</b></dt>
</dl>
</td>
<td width="60%">
This value corresponds to the error code that the WinUsb API returned.

</td>
</tr>
</table>

## -remarks

Pipe policy controls the behavior of the USB pipe (for example, time-outs, handling short packets, and so on).

For more information about valid policy types and values that a UMDF driver can pass for the <i>PolicyType</i> and <i>Value</i> parameters, see the <a href="/windows/win32/api/winusb/nf-winusb-winusb_setpipepolicy">WinUsb_SetPipePolicy</a> function.

For information about the behavior of the pipe policies, see <a href="/windows-hardware/drivers/ddi/index">WinUSB Functions for Pipe Policy Modification</a>.

The <b>SetPipePolicy</b> method generates a UMDF request and synchronously sends the request to the I/O target.


#### Examples

The following code example sets policy for input and output pipes.


```
HRESULT
CMyDevice::ConfigureUsbIoTargets(
    )
{
    HRESULT                 hr;
    USB_INTERFACE_DESCRIPTOR pInterface;
    WINUSB_PIPE_INFORMATION pipe;
    BOOL                    policy;
    DWORD                   err;
    BOOL                    result;
    LONG                    i;
    LONG                    timeout;
    ULONG                   length;

    length = sizeof(UCHAR);
    hr = m_pIUsbTargetDevice->RetrieveDeviceInformation(DEVICE_SPEED, 
                                                        &length,
                                                        &m_Speed);
    if (FAILED(hr)) {
        // Print out error.
    }
    if (SUCCEEDED(hr)) {
        // Print out device speed.
    }
    //
    // Set timeout policies for input and output pipes.
    //
    if (SUCCEEDED(hr))  {
       timeout = ENDPOINT_TIMEOUT;
       hr = m_pIUsbInputPipe->SetPipePolicy(PIPE_TRANSFER_TIMEOUT,
                                            sizeof(timeout),
                                            &timeout);
       if (FAILED(hr)) {
            // Print out cannot set timeout policy for input pipe.
       }
    }
    if (SUCCEEDED(hr))  {
       timeout = ENDPOINT_TIMEOUT;
       hr = m_pIUsbOutputPipe->SetPipePolicy(PIPE_TRANSFER_TIMEOUT,
                                             sizeof(timeout),
                                             &timeout);
       if (FAILED(hr))  {
            // Print out cannot set timeout policy for output pipe.
       }
    }
 return hr;
}
```


## -see-also

<a href="/windows-hardware/drivers/ddi/wudfusb/nn-wudfusb-iwdfusbtargetpipe">IWDFUsbTargetPipe</a>



<a href="/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbtargetpipe-retrievepipepolicy">IWDFUsbTargetPipe::RetrievePipePolicy</a>



<a href="/windows/win32/api/winusb/nf-winusb-winusb_setpipepolicy">WinUsb_SetPipePolicy</a>

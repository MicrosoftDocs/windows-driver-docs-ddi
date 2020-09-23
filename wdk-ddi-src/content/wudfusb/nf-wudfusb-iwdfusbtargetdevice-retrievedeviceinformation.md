---
UID: NF:wudfusb.IWDFUsbTargetDevice.RetrieveDeviceInformation
title: IWDFUsbTargetDevice::RetrieveDeviceInformation (wudfusb.h)
description: The RetrieveDeviceInformation method retrieves device information of the specified type.
old-location: wdf\iwdfusbtargetdevice_retrievedeviceinformation.htm
tech.root: wdf
ms.assetid: 04e3dfba-3313-4575-9956-5b1861b8212a
ms.date: 02/26/2018
keywords: ["IWDFUsbTargetDevice::RetrieveDeviceInformation"]
ms.keywords: IWDFUsbTargetDevice interface,RetrieveDeviceInformation method, IWDFUsbTargetDevice.RetrieveDeviceInformation, IWDFUsbTargetDevice::RetrieveDeviceInformation, RetrieveDeviceInformation, RetrieveDeviceInformation method, RetrieveDeviceInformation method,IWDFUsbTargetDevice interface, UMDFUSBref_3323b24f-da0c-4208-8f88-88d7198e805c.xml, umdf.iwdfusbtargetdevice_retrievedeviceinformation, wdf.iwdfusbtargetdevice_retrievedeviceinformation, wudfusb/IWDFUsbTargetDevice::RetrieveDeviceInformation
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
 - IWDFUsbTargetDevice::RetrieveDeviceInformation
 - wudfusb/IWDFUsbTargetDevice::RetrieveDeviceInformation
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFUsbTargetDevice.RetrieveDeviceInformation
---

# IWDFUsbTargetDevice::RetrieveDeviceInformation


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>RetrieveDeviceInformation</b> method retrieves device information of the specified type.

## -parameters

### -param InformationType 

[in]
The type of information that the UMDF driver requests about the device.

### -param BufferLength 

[in, out]
A pointer to a variable that, on input, contains the size, in bytes, of the buffer that <b>RetrieveDeviceInformation</b> supplies in <i>Buffer</i>. On output, this parameter contains the size that <b>RetrieveDeviceInformation</b> requires for <i>Buffer</i>.

### -param Buffer 

[out]
A pointer that receives the buffer that contains the device information.

## -returns

<b>RetrieveDeviceInformation</b> returns one of the following values: 

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

<a href="/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbtargetdevice-retrievedeviceinformation">RetrieveDeviceInformation</a> successfully retrieved the device information. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY </b></dt>
</dl>
</td>
<td width="60%">

<a href="/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbtargetdevice-retrievedeviceinformation">RetrieveDeviceInformation</a> encountered an allocation failure.

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

For information about valid information types that a UMDF driver can pass for the <i>InformationType</i> parameter, see the <a href="/windows/win32/api/winusb/nf-winusb-winusb_querydeviceinformation">WinUsb_QueryDeviceInformation</a> function.

If <i>InformationType</i> is DEVICE_SPEED (0x01), on successful return, <i>Buffer</i> indicates the operating speed of the device.  0x03 indicates high-speed or higher; 0x01 indicates full-speed or lower.

The <b>RetrieveDeviceInformation</b> method generates a UMDF request and synchronously sends the request to the I/O target.


#### Examples

For a code example of how to use the<b>RetrieveDeviceInformation</b> method, see <a href="/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbtargetpipe-setpipepolicy">IWDFUsbTargetPipe::SetPipePolicy</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfusb/nn-wudfusb-iwdfusbtargetdevice">IWDFUsbTargetDevice</a>



<a href="/windows/win32/api/winusb/nf-winusb-winusb_querydeviceinformation">WinUsb_QueryDeviceInformation</a>
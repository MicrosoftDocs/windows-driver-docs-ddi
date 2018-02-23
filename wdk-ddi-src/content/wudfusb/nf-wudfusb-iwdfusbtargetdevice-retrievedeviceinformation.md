---
UID: NF:wudfusb.IWDFUsbTargetDevice.RetrieveDeviceInformation
title: IWDFUsbTargetDevice::RetrieveDeviceInformation method
author: windows-driver-content
description: The RetrieveDeviceInformation method retrieves device information of the specified type.
old-location: wdf\iwdfusbtargetdevice_retrievedeviceinformation.htm
old-project: wdf
ms.assetid: 04e3dfba-3313-4575-9956-5b1861b8212a
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: IWDFUsbTargetDevice, RetrieveDeviceInformation method, IWDFUsbTargetDevice interface, UMDFUSBref_3323b24f-da0c-4208-8f88-88d7198e805c.xml, wdf.iwdfusbtargetdevice_retrievedeviceinformation, RetrieveDeviceInformation method, RetrieveDeviceInformation, IWDFUsbTargetDevice::RetrieveDeviceInformation, wudfusb/IWDFUsbTargetDevice::RetrieveDeviceInformation, IWDFUsbTargetDevice interface, RetrieveDeviceInformation method, umdf.iwdfusbtargetdevice_retrievedeviceinformation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
req.lib: wudfusb.h
req.dll: WUDFx.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WUDFx.dll
apiname:
-	IWDFUsbTargetDevice.RetrieveDeviceInformation
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# IWDFUsbTargetDevice::RetrieveDeviceInformation method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>RetrieveDeviceInformation</b> method retrieves device information of the specified type.


## -syntax


````
HRESULT RetrieveDeviceInformation(
  [in]      ULONG InformationType,
  [in, out] ULONG *BufferLength,
  [out]     PVOID Buffer
);
````


## -parameters




### -param InformationType [in]

The type of information that the UMDF driver requests about the device.  



### -param BufferLength [in, out]

A pointer to a variable that, on input, contains the size, in bytes, of the buffer that <b>RetrieveDeviceInformation</b> supplies in <i>Buffer</i>. On output, this parameter contains the size that <b>RetrieveDeviceInformation</b> requires for <i>Buffer</i>.


### -param Buffer [out]

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

<a href="https://msdn.microsoft.com/04e3dfba-3313-4575-9956-5b1861b8212a">RetrieveDeviceInformation</a> successfully retrieved the device information. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY </b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/04e3dfba-3313-4575-9956-5b1861b8212a">RetrieveDeviceInformation</a> encountered an allocation failure.

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



For information about valid information types that a UMDF driver can pass for the <i>InformationType</i> parameter, see the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540290">WinUsb_QueryDeviceInformation</a> function.

If <i>InformationType</i> is DEVICE_SPEED (0x01), on successful return, <i>Buffer</i> indicates the operating speed of the device.  0x03 indicates high-speed or higher; 0x01 indicates full-speed or lower.

The <b>RetrieveDeviceInformation</b> method generates a UMDF request and synchronously sends the request to the I/O target.


#### Examples

For a code example of how to use the<b>RetrieveDeviceInformation</b> method, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560421">IWDFUsbTargetPipe::SetPipePolicy</a>.

<div class="code"></div>



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540290">WinUsb_QueryDeviceInformation</a>



<a href="..\wudfusb\nn-wudfusb-iwdfusbtargetdevice.md">IWDFUsbTargetDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFUsbTargetDevice::RetrieveDeviceInformation method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


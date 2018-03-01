---
UID: NF:wudfusb.IWDFUsbTargetDevice.SetPowerPolicy
title: IWDFUsbTargetDevice::SetPowerPolicy method
author: windows-driver-content
description: The SetPowerPolicy method sets the WinUsb power policy.
old-location: wdf\iwdfusbtargetdevice_setpowerpolicy.htm
old-project: wdf
ms.assetid: e1b31df0-d383-43a3-bf9f-8874689cbf58
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IWDFUsbTargetDevice, IWDFUsbTargetDevice interface, SetPowerPolicy method, IWDFUsbTargetDevice::SetPowerPolicy, SetPowerPolicy method, SetPowerPolicy method, IWDFUsbTargetDevice interface, SetPowerPolicy,IWDFUsbTargetDevice.SetPowerPolicy, UMDFUSBref_fb6e31cc-0db6-4733-baea-d73514fb5160.xml, umdf.iwdfusbtargetdevice_setpowerpolicy, wdf.iwdfusbtargetdevice_setpowerpolicy, wudfusb/IWDFUsbTargetDevice::SetPowerPolicy
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFUsbTargetDevice.SetPowerPolicy
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# IWDFUsbTargetDevice::SetPowerPolicy method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>SetPowerPolicy</b> method sets the WinUsb power policy.


## -syntax


````
HRESULT SetPowerPolicy(
  [in] ULONG PolicyType,
  [in] ULONG ValueLength,
  [in] PVOID Value
);
````


## -parameters




### -param PolicyType [in]

The type of WinUsb power policy that the UMDF driver sets.


### -param ValueLength [in]

The size, in bytes, of the buffer that <b>SetPowerPolicy</b> supplies in <i>Value</i>.


### -param Value [in]

A pointer to the buffer that contains the WinUsb power policy.


## -returns



<b>SetPowerPolicy</b> returns one of the following values: 

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

<a href="https://msdn.microsoft.com/e1b31df0-d383-43a3-bf9f-8874689cbf58">SetPowerPolicy</a> successfully set the WinUsb power policy. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY </b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/e1b31df0-d383-43a3-bf9f-8874689cbf58">SetPowerPolicy</a> encountered an allocation failure.

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



Power policy controls the power management that WinUsb for the device performs.

For information about valid policy types and values that a UMDF driver can pass for the <i>PolicyType</i> and <i>Value</i> parameters, see the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540309">WinUsb_SetPowerPolicy</a> function.

For more information about the power behavior of WinUSB, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff728834">WinUSB Power Management</a>.

The <b>SetPowerPolicy</b> method generates a UMDF request and synchronously sends the request to the I/O target.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540309">WinUsb_SetPowerPolicy</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560379">IWDFUsbTargetDevice::RetrievePowerPolicy</a>



<a href="..\wudfusb\nn-wudfusb-iwdfusbtargetdevice.md">IWDFUsbTargetDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFUsbTargetDevice::SetPowerPolicy method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


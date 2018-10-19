---
UID: NF:wudfusb.IWDFUsbTargetDevice.RetrievePowerPolicy
title: IWDFUsbTargetDevice::RetrievePowerPolicy
author: windows-driver-content
description: The RetrievePowerPolicy method retrieves a WinUsb power policy.
old-location: wdf\iwdfusbtargetdevice_retrievepowerpolicy.htm
tech.root: wdf
ms.assetid: e15561e3-ba3d-4c65-bb6e-d90f3fab22af
ms.date: 02/26/2018
ms.keywords: IWDFUsbTargetDevice interface,RetrievePowerPolicy method, IWDFUsbTargetDevice.RetrievePowerPolicy, IWDFUsbTargetDevice::RetrievePowerPolicy, RetrievePowerPolicy, RetrievePowerPolicy method, RetrievePowerPolicy method,IWDFUsbTargetDevice interface, UMDFUSBref_50da7595-0735-475b-863e-33a689f4fc2b.xml, umdf.iwdfusbtargetdevice_retrievepowerpolicy, wdf.iwdfusbtargetdevice_retrievepowerpolicy, wudfusb/IWDFUsbTargetDevice::RetrievePowerPolicy
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
req.lib: 
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
-	IWDFUsbTargetDevice.RetrievePowerPolicy
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFUsbTargetDevice::RetrievePowerPolicy


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>RetrievePowerPolicy</b> method retrieves a WinUsb power policy.


## -parameters




### -param PolicyType [in]

The type of WinUsb power policy that the UMDF driver requests.


### -param ValueLength [in, out]

A pointer to a variable that, on input, contains the size, in bytes, of the buffer that <b>RetrievePowerPolicy</b> supplies in <i>Value</i>. On output, this parameter contains the size that <b>RetrievePowerPolicy</b> requires for <i>Value</i>.


### -param Value [out]

A pointer that receives the buffer that contains the WinUsb power policy.


## -returns



<b>RetrievePowerPolicy</b> returns one of the following values: 

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

<a href="https://msdn.microsoft.com/e15561e3-ba3d-4c65-bb6e-d90f3fab22af">RetrievePowerPolicy</a> successfully retrieved the WinUsb power policy. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY </b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/e15561e3-ba3d-4c65-bb6e-d90f3fab22af">RetrievePowerPolicy</a> encountered an allocation failure.

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

For information about valid policy types that a UMDF driver can pass for the <i>PolicyType</i> parameter and values that the framework returns, see the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540275">WinUsb_GetPowerPolicy</a> function.

For more information about the power behavior of WinUSB, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff728834">WinUSB Power Management</a>.

The <b>RetrievePowerPolicy</b> method generates a UMDF request and synchronously sends the request to the I/O target.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560362">IWDFUsbTargetDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560385">IWDFUsbTargetDevice::SetPowerPolicy</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540275">WinUsb_GetPowerPolicy</a>
 

 


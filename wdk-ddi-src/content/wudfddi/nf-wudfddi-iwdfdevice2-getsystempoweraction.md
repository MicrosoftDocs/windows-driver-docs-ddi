---
UID: NF:wudfddi.IWDFDevice2.GetSystemPowerAction
title: IWDFDevice2::GetSystemPowerAction
author: windows-driver-content
description: The GetSystemPowerAction method returns the system power action, if any, that is currently occurring for the computer.
old-location: wdf\iwdfdevice2_getsystempoweraction.htm
old-project: wdf
ms.assetid: 0030d64b-3f88-4bb3-b7d2-fcdc57d4d887
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetSystemPowerAction, GetSystemPowerAction method, GetSystemPowerAction method,IWDFDevice2 interface, IWDFDevice2 interface,GetSystemPowerAction method, IWDFDevice2.GetSystemPowerAction, IWDFDevice2::GetSystemPowerAction, UMDFDeviceObjectRef_a0135e99-c33a-4480-afb3-189d6a89b5d2.xml, umdf.iwdfdevice2_getsystempoweraction, wdf.iwdfdevice2_getsystempoweraction, wudfddi/IWDFDevice2::GetSystemPowerAction
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
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
-	IWDFDevice2.GetSystemPowerAction
product: Windows
targetos: Windows
req.typenames: 
---

# IWDFDevice2::GetSystemPowerAction


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetSystemPowerAction</b> method returns the <a href="https://msdn.microsoft.com/e8ab99d4-c18d-4ba8-bfe8-8eebb881c384">system power action</a>, if any, that is currently occurring for the computer. 


## -parameters






## -returns



<b>GetSystemPowerAction</b> returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560459">POWER_ACTION</a>-typed enumerator value. The value indicates the <a href="https://msdn.microsoft.com/e8ab99d4-c18d-4ba8-bfe8-8eebb881c384">system power action</a> that is currently occurring for the computer. For more information, see the following Remarks section. 




## -remarks



The <b>GetSystemPowerAction</b> method enables a driver to determine whether a device's power transition is occurring because the device is idle (or waking up), or because the entire computer is entering (or leaving) a low-power state. 

The driver must call <b>GetSystemPowerAction</b> only from the event callback functions that the framework calls when the device is <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/a-device-enters-a-low-power-state">entering a low-power state</a> or <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/a-device-returns-to-its-working-state">returning to its working state</a>. 

The value that <b>GetSystemPowerAction</b> returns depends on the following situations:

<ul>
<li>
If the computer is entering a low-power state when the driver calls <b>GetSystemPowerAction</b>, the method returns the reason that the computer is entering the low-power state. For example, the method returns <b>PowerActionSleep</b> if the computer is entering its S1, S2, or S3 low-power state.

</li>
<li>
If the computer is returning to its working (S0) state from a low-power state when the driver calls <b>GetSystemPowerAction</b>, the method returns the reason that the computer entered the low-power state. For example, the method returns <b>PowerActionSleep</b> if the computer is leaving its S1, S2, or S3 low-power state.

</li>
<li>
If the computer is powering up (after having been turned off) when the driver calls <b>GetSystemPowerAction</b>, the method returns <b>PowerActionNone</b>.

</li>
<li>
If the device is entering a low-power idle state or returning to its working (D0) state when the driver calls <b>GetSystemPowerAction</b>, while the rest of the system remains at its working (S0) state, the method returns <b>PowerActionNone</b>.

</li>
<li>
If the computer and the device are both in their working states when the driver calls <b>GetSystemPowerAction</b>, the method returns <b>PowerActionNone</b>.

</li>
</ul>
For more information about low-power states, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/a-device-enters-a-low-power-state">A Device Enters a Low-Power State</a>.


#### Examples

The following code example obtains the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556918">IWDFDevice2</a> interface and then calls <b>GetSystemPowerAction</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>   IWDFDevice2 *pDevice2 = NULL;
    HRESULT hrQI = pDevice-&gt;QueryInterface(IID_PPV_ARGS(&amp;pDevice2));
    if (SUCCEEDED(hrQI))
    {
        POWER_ACTION powerAction = pDevice2-&gt;GetSystemPowerAction();
    }
...
    SAFE_RELEASE(pDevice2);</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556918">IWDFDevice2</a>
 

 


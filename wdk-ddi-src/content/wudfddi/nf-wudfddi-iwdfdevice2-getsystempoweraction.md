---
UID: NF:wudfddi.IWDFDevice2.GetSystemPowerAction
title: IWDFDevice2::GetSystemPowerAction method
author: windows-driver-content
description: The GetSystemPowerAction method returns the system power action, if any, that is currently occurring for the computer.
old-location: wdf\iwdfdevice2_getsystempoweraction.htm
old-project: wdf
ms.assetid: 0030d64b-3f88-4bb3-b7d2-fcdc57d4d887
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IWDFDevice2, IWDFDevice2::GetSystemPowerAction, GetSystemPowerAction
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
req.alt-api: IWDFDevice2.GetSystemPowerAction
req.alt-loc: WUDFx.dll
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
req.typenames: *PPOWER_ACTION, POWER_ACTION
req.product: Windows 10 or later.
---

# IWDFDevice2::GetSystemPowerAction method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetSystemPowerAction</b> method returns the <a href="https://msdn.microsoft.com/e8ab99d4-c18d-4ba8-bfe8-8eebb881c384">system power action</a>, if any, that is currently occurring for the computer. 



## -syntax

````
POWER_ACTION GetSystemPowerAction();
````


## -parameters


## -returns
<b>GetSystemPowerAction</b> returns a <a href="..\ntpoapi\ne-ntpoapi-ppower_action.md">POWER_ACTION</a>-typed enumerator value. The value indicates the <a href="https://msdn.microsoft.com/e8ab99d4-c18d-4ba8-bfe8-8eebb881c384">system power action</a> that is currently occurring for the computer. For more information, see the following Remarks section. 

<b>GetSystemPowerAction</b> returns a <a href="..\ntpoapi\ne-ntpoapi-ppower_action.md">POWER_ACTION</a>-typed enumerator value. The value indicates the <a href="https://msdn.microsoft.com/e8ab99d4-c18d-4ba8-bfe8-8eebb881c384">system power action</a> that is currently occurring for the computer. For more information, see the following Remarks section. 

<b>GetSystemPowerAction</b> returns a <a href="..\ntpoapi\ne-ntpoapi-ppower_action.md">POWER_ACTION</a>-typed enumerator value. The value indicates the <a href="https://msdn.microsoft.com/e8ab99d4-c18d-4ba8-bfe8-8eebb881c384">system power action</a> that is currently occurring for the computer. For more information, see the following Remarks section. 


## -remarks
The <b>GetSystemPowerAction</b> method enables a driver to determine whether a device's power transition is occurring because the device is idle (or waking up), or because the entire computer is entering (or leaving) a low-power state. 

The driver must call <b>GetSystemPowerAction</b> only from the event callback functions that the framework calls when the device is <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/a-device-enters-a-low-power-state">entering a low-power state</a> or <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/a-device-returns-to-its-working-state">returning to its working state</a>. 

The value that <b>GetSystemPowerAction</b> returns depends on the following situations:

If the computer is entering a low-power state when the driver calls <b>GetSystemPowerAction</b>, the method returns the reason that the computer is entering the low-power state. For example, the method returns <b>PowerActionSleep</b> if the computer is entering its S1, S2, or S3 low-power state.

If the computer is returning to its working (S0) state from a low-power state when the driver calls <b>GetSystemPowerAction</b>, the method returns the reason that the computer entered the low-power state. For example, the method returns <b>PowerActionSleep</b> if the computer is leaving its S1, S2, or S3 low-power state.

If the computer is powering up (after having been turned off) when the driver calls <b>GetSystemPowerAction</b>, the method returns <b>PowerActionNone</b>.

If the device is entering a low-power idle state or returning to its working (D0) state when the driver calls <b>GetSystemPowerAction</b>, while the rest of the system remains at its working (S0) state, the method returns <b>PowerActionNone</b>.

If the computer and the device are both in their working states when the driver calls <b>GetSystemPowerAction</b>, the method returns <b>PowerActionNone</b>.

For more information about low-power states, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/a-device-enters-a-low-power-state">A Device Enters a Low-Power State</a>.

The following code example obtains the <a href="..\wudfddi\nn-wudfddi-iwdfdevice2.md">IWDFDevice2</a> interface and then calls <b>GetSystemPowerAction</b>.


## -see-also
<dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfdevice2.md">IWDFDevice2</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDevice2::GetSystemPowerAction method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


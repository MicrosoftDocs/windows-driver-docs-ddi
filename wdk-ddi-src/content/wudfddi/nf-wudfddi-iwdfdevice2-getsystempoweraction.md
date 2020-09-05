---
UID: NF:wudfddi.IWDFDevice2.GetSystemPowerAction
title: IWDFDevice2::GetSystemPowerAction (wudfddi.h)
description: The GetSystemPowerAction method returns the system power action, if any, that is currently occurring for the computer.
old-location: wdf\iwdfdevice2_getsystempoweraction.htm
tech.root: wdf
ms.assetid: 0030d64b-3f88-4bb3-b7d2-fcdc57d4d887
ms.date: 02/26/2018
keywords: ["IWDFDevice2::GetSystemPowerAction"]
ms.keywords: GetSystemPowerAction, GetSystemPowerAction method, GetSystemPowerAction method,IWDFDevice2 interface, IWDFDevice2 interface,GetSystemPowerAction method, IWDFDevice2.GetSystemPowerAction, IWDFDevice2::GetSystemPowerAction, UMDFDeviceObjectRef_a0135e99-c33a-4480-afb3-189d6a89b5d2.xml, umdf.iwdfdevice2_getsystempoweraction, wdf.iwdfdevice2_getsystempoweraction, wudfddi/IWDFDevice2::GetSystemPowerAction
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDFDevice2::GetSystemPowerAction
 - wudfddi/IWDFDevice2::GetSystemPowerAction
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFDevice2.GetSystemPowerAction
---

# IWDFDevice2::GetSystemPowerAction


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetSystemPowerAction</b> method returns the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/system-power-actions">system power action</a>, if any, that is currently occurring for the computer.

## -returns

<b>GetSystemPowerAction</b> returns a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-ppower_action">POWER_ACTION</a>-typed enumerator value. The value indicates the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/system-power-actions">system power action</a> that is currently occurring for the computer. For more information, see the following Remarks section.

## -remarks

The <b>GetSystemPowerAction</b> method enables a driver to determine whether a device's power transition is occurring because the device is idle (or waking up), or because the entire computer is entering (or leaving) a low-power state. 

The driver must call <b>GetSystemPowerAction</b> only from the event callback functions that the framework calls when the device is <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/a-device-enters-a-low-power-state">entering a low-power state</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/a-device-returns-to-its-working-state">returning to its working state</a>. 

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
For more information about low-power states, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/a-device-enters-a-low-power-state">A Device Enters a Low-Power State</a>.


#### Examples

The following code example obtains the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice2">IWDFDevice2</a> interface and then calls <b>GetSystemPowerAction</b>.


```
   IWDFDevice2 *pDevice2 = NULL;
    HRESULT hrQI = pDevice->QueryInterface(IID_PPV_ARGS(&pDevice2));
    if (SUCCEEDED(hrQI))
    {
        POWER_ACTION powerAction = pDevice2->GetSystemPowerAction();
    }
...
    SAFE_RELEASE(pDevice2);
```


## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice2">IWDFDevice2</a>


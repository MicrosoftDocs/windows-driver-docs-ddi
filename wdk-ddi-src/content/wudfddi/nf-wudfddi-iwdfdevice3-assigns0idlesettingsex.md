---
UID: NF:wudfddi.IWDFDevice3.AssignS0IdleSettingsEx
title: IWDFDevice3::AssignS0IdleSettingsEx
author: windows-driver-content
description: The AssignS0IdleSettingsEx method provides driver-supplied information that the framework uses when a device is idle and the system is in its working (S0) state.
old-location: wdf\iwdfdevice3_assigns0idlesettingsex.htm
tech.root: wdf
ms.assetid: D020B8AA-7353-47E1-A111-82BFE6F5F03D
ms.date: 02/26/2018
ms.keywords: AssignS0IdleSettingsEx, AssignS0IdleSettingsEx method, AssignS0IdleSettingsEx method,IWDFDevice3 interface, IWDFDevice3 interface,AssignS0IdleSettingsEx method, IWDFDevice3.AssignS0IdleSettingsEx, IWDFDevice3::AssignS0IdleSettingsEx, umdf.iwdfdevice3_assigns0idlesettingsex, wdf.iwdfdevice3_assigns0idlesettingsex, wudfddi/IWDFDevice3::AssignS0IdleSettingsEx
ms.topic: method
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
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
-	IWDFDevice3.AssignS0IdleSettingsEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFDevice3::AssignS0IdleSettingsEx


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The 
  <b>AssignS0IdleSettingsEx</b> method provides driver-supplied information that the framework uses when a device is idle and the system is in its working (S0) state.


## -parameters




### -param IdleSettings [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh464078">WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure that was initialized by a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh464080">WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT</a> macro.


## -returns



The method returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.




## -remarks



A driver can call <b>AssignS0IdleSettingsEx</b> at any point after the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a>. Before calling  <b>IWDFDriver::CreateDevice</b>, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff557001">IWDFDeviceInitialize::SetPowerPolicyOwnership</a> with  the <i>fTrue</i> parameter set to <b>TRUE</b>. For an example of this call sequence, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a>.

If your driver calls <b>AssignS0IdleSettingsEx</b> more than once, follow the rules described in the Remarks section of <a href="https://msdn.microsoft.com/ffe91b9a-3b74-4dd9-b23d-096f1992485e">AssignS0IdleSettings</a>.

For more information about idle power-down, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-idle-power-down-in-umdf-drivers">Supporting Idle Power-Down in UMDF-based Drivers</a>.


#### Examples

The following code example initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/hh464078">WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure and sets an idle time-out value of 10 seconds. The example then obtains the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451197">IWDFDevice3</a> interface and calls <b>AssignS0IdleSettingsEx</b>. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>IWDFDevice3 *pIWDFDevice3 = NULL;
HRESULT hr;

WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS  idleSettings;

WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT(
                                           &amp;idleSettings,
                                           IdleCanWakeFromS0
                                           );
idleSettings.IdleTimeout = 10000;

//
// Get a pointer to the IWDFDevice3 interface.
//

hr = pIWDFDevice-&gt;QueryInterface(__uuidof(IWDFDevice3),
                                 (void**) &amp;pIWDFDevice3);
if (SUCCEEDED(hr)) 
   {
    
   hr = pIWDFDevice3-&gt;AssignS0IdleSettingsEx(&amp;idleSettings
                                            );
   }
...

SAFE_RELEASE(pIWDFDevice3);
   </pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556920">IWDFDevice2::AssignS0IdleSettings</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451197">IWDFDevice3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545903">WdfDeviceAssignS0IdleSettings</a>
 

 


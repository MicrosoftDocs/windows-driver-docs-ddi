---
UID: NF:wudfdevice.WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT
title: WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT function (wudfdevice.h)
description: The WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT function initializes a driver's WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS structure.
old-location: wdf\wudf_device_power_policy_idle_settings_init.htm
tech.root: wdf
ms.assetid: 893F249B-ACD9-4262-93B6-890987A9F591
ms.date: 02/26/2018
keywords: ["WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT function"]
ms.keywords: WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT, WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT function, umdf.wudf_device_power_policy_idle_settings_init, wdf.wudf_device_power_policy_idle_settings_init, wudfdevice/WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT
f1_keywords:
 - "wudfdevice/WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT"
 - "WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT"
req.header: wudfdevice.h
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
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wudfdevice.h
api_name:
- WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT
targetos: Windows
req.typenames: 
---

# WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT function


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT</b> function initializes a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi_types/ns-wudfddi_types-_wudf_device_power_policy_idle_settings">WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure.


## -parameters




### -param Settings 
[out]
A pointer to a driver-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi_types/ns-wudfddi_types-_wudf_device_power_policy_idle_settings">WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure.


### -param IdleCaps 
[in]
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_power_policy_s0_idle_capabilities">WDF_POWER_POLICY_S0_IDLE_CAPABILITIES</a>-typed enumerator.


## -remarks



First, the <b>WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT</b> function zeros the specified <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi_types/ns-wudfddi_types-_wudf_device_power_policy_idle_settings">WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure and sets the structure's <b>Size</b> member. 

Then, the function sets the structure's <b>IdleTimeout</b> member to <b>IdleTimeoutDefaultValue</b>, sets the <b>UserControlOfIdleSettings</b> member to <b>IdleAllowUserControl</b>, and sets the <b>Enabled</b> member to <b>WdfUseDefault</b>. 

In addition, the function sets the <b>PowerUpIdleDeviceOnSystemWake</b> member to  <b>WdfUseDefault</b>.

 The function then sets the <b>ExcludeD3Cold</b> member to <b>WdfUseDefault</b>.

Next, the function sets the structure's <b>IdleCaps</b> member to the value that the <i>IdleCaps</i> parameter specifies. 

Finally, if the <i>IdleCaps</i> parameter specifies <b>IdleUsbSelectiveSuspend</b> or <b>IdleCanWakeFromS0</b>, the function sets the <b>DxState</b> member to <b>PowerDeviceMaximum</b>. If the <i>IdleCaps</i> parameter specifies <b>IdleCannotWakeFromS0</b>, the function sets the <b>DxState</b> member to <b>PowerDeviceD3</b>.

For a code example that uses <b>WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice3-assigns0idlesettingsex">IWDFDevice3::AssignS0IdleSettingsEx</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice3-assigns0idlesettingsex">IWDFDevice3::AssignS0IdleSettingsEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi_types/ns-wudfddi_types-_wudf_device_power_policy_idle_settings">WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a>
 

 


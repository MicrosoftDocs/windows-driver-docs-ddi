---
UID: NF:wudfdevice.WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT
title: WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT function
author: windows-driver-content
description: The WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT function initializes a driver's WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS structure.
old-location: wdf\wudf_device_power_policy_idle_settings_init.htm
old-project: wdf
ms.assetid: 893F249B-ACD9-4262-93B6-890987A9F591
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.wudf_device_power_policy_idle_settings_init, WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT, wudfdevice/WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT, WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT function, umdf.wudf_device_power_policy_idle_settings_init
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wudfdevice.h
apiname:
-	WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT
product: Windows
targetos: Windows
req.typenames: WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS, *PWUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS
req.product: Windows 10 or later.
---

# WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT function


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT</b> function initializes a driver's <a href="..\wudfddi_types\ns-wudfddi_types-_wudf_device_power_policy_idle_settings.md">WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure.


## -syntax


````
void WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT(
  _Out_ PWUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS Settings,
  _In_  WDF_POWER_POLICY_S0_IDLE_CAPABILITIES   IdleCaps
);
````


## -parameters




### -param Settings [out]

A pointer to a driver-allocated <a href="..\wudfddi_types\ns-wudfddi_types-_wudf_device_power_policy_idle_settings.md">WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure.


### -param IdleCaps [in]

A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_power_policy_s0_idle_capabilities.md">WDF_POWER_POLICY_S0_IDLE_CAPABILITIES</a>-typed enumerator.


## -returns


This function does not return a value.



## -remarks


First, the <b>WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT</b> function zeros the specified <a href="..\wudfddi_types\ns-wudfddi_types-_wudf_device_power_policy_idle_settings.md">WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure and sets the structure's <b>Size</b> member. 

Then, the function sets the structure's <b>IdleTimeout</b> member to <b>IdleTimeoutDefaultValue</b>, sets the <b>UserControlOfIdleSettings</b> member to <b>IdleAllowUserControl</b>, and sets the <b>Enabled</b> member to <b>WdfUseDefault</b>. 

In addition, the function sets the <b>PowerUpIdleDeviceOnSystemWake</b> member to  <b>WdfUseDefault</b>.

 The function then sets the <b>ExcludeD3Cold</b> member to <b>WdfUseDefault</b>.

Next, the function sets the structure's <b>IdleCaps</b> member to the value that the <i>IdleCaps</i> parameter specifies. 

Finally, if the <i>IdleCaps</i> parameter specifies <b>IdleUsbSelectiveSuspend</b> or <b>IdleCanWakeFromS0</b>, the function sets the <b>DxState</b> member to <b>PowerDeviceMaximum</b>. If the <i>IdleCaps</i> parameter specifies <b>IdleCannotWakeFromS0</b>, the function sets the <b>DxState</b> member to <b>PowerDeviceD3</b>.

For a code example that uses <b>WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT</b>, see <a href="https://msdn.microsoft.com/D020B8AA-7353-47E1-A111-82BFE6F5F03D">IWDFDevice3::AssignS0IdleSettingsEx</a>.



## -see-also

<a href="..\wudfddi_types\ns-wudfddi_types-_wudf_device_power_policy_idle_settings.md">WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a>

<a href="https://msdn.microsoft.com/D020B8AA-7353-47E1-A111-82BFE6F5F03D">IWDFDevice3::AssignS0IdleSettingsEx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


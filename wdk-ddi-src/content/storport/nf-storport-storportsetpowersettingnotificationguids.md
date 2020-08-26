---
UID: NF:storport.StorPortSetPowerSettingNotificationGuids
title: StorPortSetPowerSettingNotificationGuids function (storport.h)
description: The StorPortSetPowerSettingNotificationGuids routine enables a miniport to receive power setting notifications. The miniport registers an array of GUIDs which identify the power settings to receive power change notifications for.
old-location: storage\storportsetpowersettingnotificationguids.htm
tech.root: storage
ms.assetid: FB74E774-8CDE-4DE4-942E-10AF4BEFF63C
ms.date: 03/29/2018
keywords: ["StorPortSetPowerSettingNotificationGuids function"]
ms.keywords: Adaptive Setting, HIPM/DIPM Setting, StorPortSetPowerSettingNotificationGuids, StorPortSetPowerSettingNotificationGuids routine [Storage Devices], storage.storportsetpowersettingnotificationguids, storport/StorPortSetPowerSettingNotificationGuids
f1_keywords:
 - "storport/StorPortSetPowerSettingNotificationGuids"
 - "StorPortSetPowerSettingNotificationGuids"
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available in starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- storport.h
api_name:
- StorPortSetPowerSettingNotificationGuids
targetos: Windows
req.typenames: 
---

# StorPortSetPowerSettingNotificationGuids function


## -description


The <b>StorPortSetPowerSettingNotificationGuids</b> routine enables a miniport to receive power setting notifications. The miniport registers an array of GUIDs which identify the power settings to receive power change notifications for.


## -parameters




### -param HwDeviceExtension 
[in]
A pointer to the hardware device extension for the host bus adapter (HBA).


### -param GuidCount 
[in]
The number of GUIDs in the <i>Guid</i> array.


### -param Guid 
[in]
An array of power setting GUIDs to register for notification. A typical use for registering these GUIDs is for SATA miniports to receive notifications for AHCI Link Power Management setting changes. The  AHCI Link Power Management settings defined by the Microsoft AHCI StorPort miniport driver are the following.



#### HIPM/DIPM Setting (0b2d69d7-a2a1-449c-9680-f91c70521c60)

Configures the link power management mode for disk and storage devices that are attached to the system through an AHCI interface.

<table>
<tr>
<th>Index</th>
<th>Name</th>
<th>Description</th>
</tr>
<tr>
<td>0</td>
<td>Active</td>
<td>Link power management is not used.</td>
</tr>
<tr>
<td>1</td>
<td>HIPM</td>
<td>Host-Initiated Power Management (HIPM) is used.</td>
</tr>
<tr>
<td>2</td>
<td>HIPM and DIPM</td>
<td>HIPM and Device-Initiated Power Management (DIPM) are used.</td>
</tr>
</table>
 



#### Adaptive Setting (dab60367-53fe-4fbc-825e-521d069d2456)

The period of AHCI link idle time before the link is put into a slumber state when HIPM or DIPM is enabled.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0</td>
<td>Minimum value in milliseconds (only use Partial state).</td>
</tr>
<tr>
<td>...</td>
<td>Any intermediate value.</td>
</tr>
<tr>
<td>300000</td>
<td>Maximum value in milliseconds (5 minutes).</td>
</tr>
</table>
 

Other miniports may define and register their own power setting GUIDs.


## -returns



The <b>StorPortSetPowerSettingNotificationGuids</b> routine returns one of these status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
 Insufficient resources are available to register for notifications.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The notification GUIDs were registered successfully.

</td>
</tr>
</table>
 




## -remarks



A miniport calls <b>StorPortSetPowerSettingNotificationGuids</b> in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nc-storport-hw_find_adapter">HwStorFindAdapter</a> routine to register the GUIDs it requests to receive notifications for.

When a power state change occurs for a registered notification, the miniport is notified in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nc-storport-hw_adapter_control">HwStorAdapterControl</a> routine. The control type of <b>ScsiPowerSettingNotification</b> is set in the <i>ControlType</i> parameter.

The AHCI Link Power management settings are part of the Disk Settings subgroup (0012ee47-9041-4b5d-9b77-535fba8b1442) in the power policy configuration. These are managed under the SUB_DISK configuration  alias with <i>powercfg.exe</i>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nc-storport-hw_adapter_control">HwStorAdapterControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nc-storport-hw_find_adapter">HwStorFindAdapter</a>
 

 


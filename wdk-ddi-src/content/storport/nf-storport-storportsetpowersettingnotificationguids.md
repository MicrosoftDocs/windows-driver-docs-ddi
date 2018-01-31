---
UID: NF:storport.StorPortSetPowerSettingNotificationGuids
title: StorPortSetPowerSettingNotificationGuids function
author: windows-driver-content
description: The StorPortSetPowerSettingNotificationGuids routine enables a miniport to receive power setting notifications. The miniport registers an array of GUIDs which identify the power settings to receive power change notifications for.
old-location: storage\storportsetpowersettingnotificationguids.htm
old-project: storage
ms.assetid: FB74E774-8CDE-4DE4-942E-10AF4BEFF63C
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: Adaptive Setting, StorPortSetPowerSettingNotificationGuids routine [Storage Devices], StorPortSetPowerSettingNotificationGuids, HIPM/DIPM Setting, storage.storportsetpowersettingnotificationguids, storport/StorPortSetPowerSettingNotificationGuids
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: Any
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	storport.h
apiname:
-	StorPortSetPowerSettingNotificationGuids
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortSetPowerSettingNotificationGuids function


## -description


The <b>StorPortSetPowerSettingNotificationGuids</b> routine enables a miniport to receive power setting notifications. The miniport registers an array of GUIDs which identify the power settings to receive power change notifications for.


## -syntax


````
ULONG StorPortSetPowerSettingNotificationGuids(
  _In_ PVOID  HwDeviceExtension,
  _In_ ULONG  GuidCount,
  _In_ LPGUID Guid
);
````


## -parameters




#### - HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


#### - GuidCount [in]

The number of GUIDs in the <i>Guid</i> array.


#### - Guid [in]

An array of power setting GUIDs to register for notification. A typical use for registering these GUIDs is for SATA miniports to receive notifications for AHCI Link Power Management setting changes. The  AHCI Link Power Management settings defined by the Microsoft AHCI StorPort miniport driver are the following.

Other miniports may define and register their own power setting GUIDs.


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


A miniport calls <b>StorPortSetPowerSettingNotificationGuids</b> in its <a href="..\storport\nc-storport-hw_find_adapter.md">HwStorFindAdapter</a> routine to register the GUIDs it requests to receive notifications for.

When a power state change occurs for a registered notification, the miniport is notified in its <a href="..\storport\nc-storport-hw_adapter_control.md">HwStorAdapterControl</a> routine. The control type of <b>ScsiPowerSettingNotification</b> is set in the <i>ControlType</i> parameter.

The AHCI Link Power management settings are part of the Disk Settings subgroup (0012ee47-9041-4b5d-9b77-535fba8b1442) in the power policy configuration. These are managed under the SUB_DISK configuration  alias with <i>powercfg.exe</i>.



## -see-also

<a href="..\storport\nc-storport-hw_adapter_control.md">HwStorAdapterControl</a>

<a href="..\storport\nc-storport-hw_find_adapter.md">HwStorFindAdapter</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortSetPowerSettingNotificationGuids routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


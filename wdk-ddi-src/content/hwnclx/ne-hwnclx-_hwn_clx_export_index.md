---
UID: NE:hwnclx._HWN_CLX_EXPORT_INDEX
title: "_HWN_CLX_EXPORT_INDEX"
author: windows-driver-content
description: Defines the position for each of the Hardware Notification exports in the export table.
old-location: gpiobtn\_hwn_clx_export_index.htm
tech.root: gpiobtn
ms.assetid: fcbbd188-438a-4eaa-8034-67ca52d1fb56
ms.date: 2/15/2018
ms.keywords: "*PHWN_CLX_EXPORT_INDEX, AddDevicePostDeviceCreateIndex, AddDevicePreDeviceCreateIndex, HWN_CLX_EXPORT_INDEX, HWN_CLX_EXPORT_INDEX enumeration, HwNExportLastExportIndex, RegisterClientIndex, UnregisterClientIndex, _HWN_CLX_EXPORT_INDEX, gpiobtn._hwn_clx_export_index, hwnclx/AddDevicePostDeviceCreateIndex, hwnclx/AddDevicePreDeviceCreateIndex, hwnclx/HWN_CLX_EXPORT_INDEX, hwnclx/HwNExportLastExportIndex, hwnclx/RegisterClientIndex, hwnclx/UnregisterClientIndex"
ms.topic: enum
req.header: hwnclx.h
req.include-header:
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Hwnclx.h
api_name:
-	HWN_CLX_EXPORT_INDEX
product:
- Windows
targetos: Windows
req.typenames: HWN_CLX_EXPORT_INDEX, *PHWN_CLX_EXPORT_INDEX
---

# _HWN_CLX_EXPORT_INDEX enumeration


## -description


Defines the position for each of the Hardware Notification exports in the export table.



## -syntax


```cpp
typedef enum _HWN_CLX_EXPORT_INDEX {
  RegisterClientIndex             = 0x0,
  UnregisterClientIndex,
  AddDevicePreDeviceCreateIndex,
  AddDevicePostDeviceCreateIndex,
  HwNExportLastExportIndex
} HWN_CLX_EXPORT_INDEX;
```


## -enum-fields




### -field RegisterClientIndex

Position of the <a href="..\hwnclx\nf-hwnclx-hwnregisterclient.md">HwNRegisterClient</a> hardware notification in the export table.



### -field UnregisterClientIndex

Position of the <a href="..\hwnclx\nf-hwnclx-hwnunregisterclient.md">HwNUnregisterClient</a> hardware notification in the export table.



### -field AddDevicePreDeviceCreateIndex

Position of the <a href="..\hwnclx\nf-hwnclx-hwnprocessadddevicepredevicecreate.md">HwNProcessAddDevicePreDeviceCreate</a> hardware notification in the export table.



### -field AddDevicePostDeviceCreateIndex

Position of the <a href="..\hwnclx\nf-hwnclx-hwnprocessadddevicepostdevicecreate.md">HwNProcessAddDevicePostDeviceCreate</a> hardware notification in the export table.



### -field HwNExportLastExportIndex

Position of the last hardware notification in the export table.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn789335">Hardware notifications support</a>



<a href="https://msdn.microsoft.com/405ff6db-9bc0-42f3-a740-49dd3967a8b3">Hardware notifications reference</a>



 

 



---
UID: NE:pcivirt._SRIOV_PF_EVENT
title: _SRIOV_PF_EVENT (pcivirt.h)
description: Defines event values for the SR-IOV device.
old-location: pci\sriov_pf_event.htm
tech.root: PCI
ms.assetid: e2b40a9d-57e6-49b1-839a-d34acb108807
ms.date: 02/24/2018
keywords: ["_SRIOV_PF_EVENT enumeration"]
ms.keywords: "*PSRIOV_PF_EVENT, PCI.sriov_pf_event, SRIOV_PF_EVENT, SRIOV_PF_EVENT enumeration [Buses], SriovEventPfMaximum, SriovEventPfQueryStopDevice, SriovEventPfRestart, _SRIOV_PF_EVENT, pcivirt/SRIOV_PF_EVENT, pcivirt/SriovEventPfMaximum, pcivirt/SriovEventPfQueryStopDevice, pcivirt/SriovEventPfRestart"
f1_keywords:
 - "pcivirt/SRIOV_PF_EVENT"
 - "SRIOV_PF_EVENT"
req.header: pcivirt.h
req.include-header:
req.target-type: Windows
req.target-min-winverclnt:
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Pcivirt.h
api_name:
- SRIOV_PF_EVENT
targetos: Windows
req.typenames: SRIOV_PF_EVENT, *PSRIOV_PF_EVENT
---

# _SRIOV_PF_EVENT enumeration


## -description


Defines event values for the SR-IOV device.


## -syntax


```cpp
typedef enum _SRIOV_PF_EVENT {
  SriovEventPfQueryStopDevice,
  SriovEventPfRestart,
  SriovEventPfMaximum
} SRIOV_PF_EVENT;
```


## -enum-fields




### -field SriovEventPfQueryStopDevice

The SR-IOV device is stopped.


### -field SriovEventPfRestart

The SR-IOV device is restarted


### -field SriovEventPfMaximum

Reserved.


## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pcivirt/ni-pcivirt-ioctl_sriov_event_complete">IOCTL_SRIOV_EVENT_COMPLETE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pcivirt/ni-pcivirt-ioctl_sriov_notification">IOCTL_SRIOV_NOTIFICATION</a>



 

 



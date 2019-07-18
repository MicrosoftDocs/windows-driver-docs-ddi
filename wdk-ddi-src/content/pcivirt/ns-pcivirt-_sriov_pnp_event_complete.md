---
UID: NS:pcivirt._SRIOV_PNP_EVENT_COMPLETE
title: _SRIOV_PNP_EVENT_COMPLETE (pcivirt.h)
description: Stores the status for an event that the SR-IOV Physical Function (PF) driver should set for Plug and Play even completion. This structure is used in the input buffer of the IOCTL_SRIOV_EVENT_COMPLETE request.
old-location: pci\sriov_pnp_event_complete.htm
tech.root: PCI
ms.assetid: 3b40d780-8084-4c19-bb8e-9d1ab3dadc95
ms.date: 02/24/2018
ms.keywords: "*PSRIOV_PNP_EVENT_COMPLETE, PCI.sriov_pnp_event_complete, SRIOV_PNP_EVENT_COMPLETE, SRIOV_PNP_EVENT_COMPLETE structure [Buses], _SRIOV_PNP_EVENT_COMPLETE, pcivirt/SRIOV_PNP_EVENT_COMPLETE"
ms.topic: struct
f1_keywords:
 - "pcivirt/SRIOV_PNP_EVENT_COMPLETE"
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
- SRIOV_PNP_EVENT_COMPLETE
product:
- Windows
targetos: Windows
req.typenames: SRIOV_PNP_EVENT_COMPLETE, *PSRIOV_PNP_EVENT_COMPLETE
---

# _SRIOV_PNP_EVENT_COMPLETE structure


## -description


Stores the status for an event that the SR-IOV Physical Function (PF) driver should set for Plug and Play even completion. This structure is used in the input buffer of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pcivirt/ni-pcivirt-ioctl_sriov_event_complete">IOCTL_SRIOV_EVENT_COMPLETE</a> request.


## -syntax


```cpp
typedef struct _SRIOV_PNP_EVENT_COMPLETE {
  NTSTATUS  QueryStatus;
} SRIOV_PNP_EVENT_COMPLETE, SRIOV_PNP_EVENT_COMPLETE;
```


## -struct-fields




### -field QueryStatus

Indicates the status to be returned in the PnP query IRP that is currently pended in the PF driver.


## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pcivirt/ni-pcivirt-ioctl_sriov_event_complete">IOCTL_SRIOV_EVENT_COMPLETE</a>



 

 



---
UID: NE:pcivirt._SRIOV_PF_EVENT
title: "_SRIOV_PF_EVENT"
author: windows-driver-content
description: Defines event values for the SR-IOV device.
old-location: pci\sriov_pf_event.htm
old-project: PCI
ms.assetid: e2b40a9d-57e6-49b1-839a-d34acb108807
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PSRIOV_PF_EVENT, PCI.sriov_pf_event, SRIOV_PF_EVENT, SRIOV_PF_EVENT enumeration [Buses], SriovEventPfMaximum, SriovEventPfQueryStopDevice, SriovEventPfRestart, _SRIOV_PF_EVENT, pcivirt/SRIOV_PF_EVENT, pcivirt/SriovEventPfMaximum, pcivirt/SriovEventPfQueryStopDevice, pcivirt/SriovEventPfRestart"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Pcivirt.h
api_name:
-	SRIOV_PF_EVENT
product: Windows
targetos: Windows
req.typenames: SRIOV_PF_EVENT, *PSRIOV_PF_EVENT
---

# _SRIOV_PF_EVENT enumeration


## -description


Defines event values for the SR-IOV device.


## -syntax


````
typedef enum _SRIOV_PF_EVENT { 
  SriovEventPfQueryStopDevice,
  SriovEventPfRestart,
  SriovEventPfMaximum
} SRIOV_PF_EVENT;
````


## -enum-fields




### -field SriovEventPfQueryStopDevice

The SR-IOV device is stopped.


### -field SriovEventPfRestart

The SR-IOV device is restarted


### -field SriovEventPfMaximum

Reserved.


## -see-also

<a href="https://msdn.microsoft.com/5299ec17-1fcb-4449-9ec4-73a4d818df0d">IOCTL_SRIOV_EVENT_COMPLETE</a>



<a href="https://msdn.microsoft.com/3f2d67e0-abab-40a1-b4a9-cb65e81884e9">IOCTL_SRIOV_NOTIFICATION</a>



 

 



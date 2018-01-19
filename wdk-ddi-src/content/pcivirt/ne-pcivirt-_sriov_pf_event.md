---
UID: NE:pcivirt._SRIOV_PF_EVENT
title: _SRIOV_PF_EVENT
author: windows-driver-content
description: Defines event values for the SR-IOV device.
old-location: pci\sriov_pf_event.htm
old-project: PCI
ms.assetid: e2b40a9d-57e6-49b1-839a-d34acb108807
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _SRIOV_PF_EVENT, SRIOV_PF_EVENT, *PSRIOV_PF_EVENT
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
req.alt-api: SRIOV_PF_EVENT
req.alt-loc: Pcivirt.h
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


## -remarks


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/3f2d67e0-abab-40a1-b4a9-cb65e81884e9">IOCTL_SRIOV_NOTIFICATION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/5299ec17-1fcb-4449-9ec4-73a4d818df0d">IOCTL_SRIOV_EVENT_COMPLETE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20SRIOV_PF_EVENT enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


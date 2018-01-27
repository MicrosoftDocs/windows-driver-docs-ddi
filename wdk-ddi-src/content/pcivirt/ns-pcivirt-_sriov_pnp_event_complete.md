---
UID: NS:pcivirt._SRIOV_PNP_EVENT_COMPLETE
title: _SRIOV_PNP_EVENT_COMPLETE
author: windows-driver-content
description: Stores the status for an event that the SR-IOV Physical Function (PF) driver should set for Plug and Play even completion. This structure is used in the input buffer of the IOCTL_SRIOV_EVENT_COMPLETE request.
old-location: pci\sriov_pnp_event_complete.htm
old-project: PCI
ms.assetid: 3b40d780-8084-4c19-bb8e-9d1ab3dadc95
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: SRIOV_PNP_EVENT_COMPLETE, SRIOV_PNP_EVENT_COMPLETE structure [Buses], _SRIOV_PNP_EVENT_COMPLETE, *PSRIOV_PNP_EVENT_COMPLETE, pcivirt/SRIOV_PNP_EVENT_COMPLETE, PCI.sriov_pnp_event_complete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	Pcivirt.h
apiname: 
-	SRIOV_PNP_EVENT_COMPLETE
product: Windows
targetos: Windows
req.typenames: *PSRIOV_PNP_EVENT_COMPLETE, SRIOV_PNP_EVENT_COMPLETE
---

# _SRIOV_PNP_EVENT_COMPLETE structure


## -description


Stores the status for an event that the SR-IOV Physical Function (PF) driver should set for Plug and Play even completion. This structure is used in the input buffer of the <a href="https://msdn.microsoft.com/5299ec17-1fcb-4449-9ec4-73a4d818df0d">IOCTL_SRIOV_EVENT_COMPLETE</a> request.


## -syntax


````
typedef struct _SRIOV_PNP_EVENT_COMPLETE {
  NTSTATUS  QueryStatus;
} SRIOV_PNP_EVENT_COMPLETE, SRIOV_PNP_EVENT_COMPLETE;
````


## -struct-fields




### -field QueryStatus

Indicates the status to be returned in the PnP query IRP that is currently pended in the PF driver.


## -see-also

<a href="https://msdn.microsoft.com/5299ec17-1fcb-4449-9ec4-73a4d818df0d">IOCTL_SRIOV_EVENT_COMPLETE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20SRIOV_PNP_EVENT_COMPLETE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


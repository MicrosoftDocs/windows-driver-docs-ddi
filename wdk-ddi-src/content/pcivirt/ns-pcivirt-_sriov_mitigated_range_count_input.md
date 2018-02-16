---
UID: NS:pcivirt._SRIOV_MITIGATED_RANGE_COUNT_INPUT
title: "_SRIOV_MITIGATED_RANGE_COUNT_INPUT"
author: windows-driver-content
description: This structure is used as an input buffer to the IOCTL_SRIOV_QUERY_MITIGATED_RANGE_COUNT request to determine the ranges of memory-mapped I/O space that must be mitigated.
old-location: pci\sriov_mitigated_range_count_input.htm
old-project: PCI
ms.assetid: 7de35a35-2b90-421d-bbde-4c5cb760070a
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: SRIOV_MITIGATED_RANGE_COUNT_INPUT structure [Buses], _SRIOV_MITIGATED_RANGE_COUNT_INPUT, SRIOV_MITIGATED_RANGE_COUNT_INPUT, *PSRIOV_MITIGATED_RANGE_COUNT_INPUT, PCI.sriov_mitigated_range_count_input, pcivirt/SRIOV_MITIGATED_RANGE_COUNT_INPUT
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
-	SRIOV_MITIGATED_RANGE_COUNT_INPUT
product: Windows
targetos: Windows
req.typenames: "*PSRIOV_MITIGATED_RANGE_COUNT_INPUT, SRIOV_MITIGATED_RANGE_COUNT_INPUT"
---

# _SRIOV_MITIGATED_RANGE_COUNT_INPUT structure


## -description


This structure is used as an input buffer to the <a href="https://msdn.microsoft.com/68fd97a5-b7ea-43c0-96ed-b64445fd21dd">IOCTL_SRIOV_QUERY_MITIGATED_RANGE_COUNT</a> request to determine the ranges of memory-mapped I/O space that must be mitigated. 


## -syntax


````
typedef struct _SRIOV_MITIGATED_RANGE_COUNT_INPUT {
  USHORT  VfIndex;
} SRIOV_MITIGATED_RANGE_COUNT_INPUT, SRIOV_MITIGATED_RANGE_COUNT_INPUT;
````


## -struct-fields




### -field VfIndex

Zero-based index of the virtual function from the first virtual function exposed by this physical function.


## -see-also

<a href="https://msdn.microsoft.com/68fd97a5-b7ea-43c0-96ed-b64445fd21dd">IOCTL_SRIOV_QUERY_MITIGATED_RANGE_COUNT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20SRIOV_MITIGATED_RANGE_COUNT_INPUT structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


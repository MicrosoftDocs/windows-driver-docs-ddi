---
UID: NS:iscsifnd._ReportDiscoveredTargets2_OUT
title: "_ReportDiscoveredTargets2_OUT"
author: windows-driver-content
description: The ReportDiscoveredTargets2_OUT structure holds the output data for the ReportDiscoveredTargets2 method.
old-location: storage\reportdiscoveredtargets2_out.htm
tech.root: storage
ms.assetid: 24e47733-14c2-4d2c-8b0a-8cdfd68c8b3b
ms.date: 3/29/2018
ms.keywords: "*PReportDiscoveredTargets2_OUT, PReportDiscoveredTargets2_OUT, PReportDiscoveredTargets2_OUT structure pointer [Storage Devices], ReportDiscoveredTargets2_OUT, ReportDiscoveredTargets2_OUT structure [Storage Devices], _ReportDiscoveredTargets2_OUT, iscsifnd/PReportDiscoveredTargets2_OUT, iscsifnd/ReportDiscoveredTargets2_OUT, storage.reportdiscoveredtargets2_out, structs-iSCSI_b6c57e31-b994-4873-97e5-87499d4ce120.xml"
ms.topic: struct
req.header: iscsifnd.h
req.include-header: Iscsifnd.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	iscsifnd.h
api_name:
-	ReportDiscoveredTargets2_OUT
product:
- Windows
targetos: Windows
req.typenames: ReportDiscoveredTargets2_OUT, *PReportDiscoveredTargets2_OUT
---

# _ReportDiscoveredTargets2_OUT structure


## -description


The ReportDiscoveredTargets2_OUT structure holds the output data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564051">ReportDiscoveredTargets2</a> method.


## -struct-fields




### -field Status

On output, the status of the <b>ReportDiscoveredTargets</b> operation. For a list of status qualifiers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>. 


### -field TargetCount

On output, the number of targets that are discovered. 


### -field Targets

On output, an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff561503">ISCSI_DiscoveredTarget2</a> structures, which provide information that is related to discovered targets. 


## -remarks



You must implement this method.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561503">ISCSI_DiscoveredTarget2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564051">ReportDiscoveredTargets2</a>
 

 


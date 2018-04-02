---
UID: NS:iscsifnd._ReportDiscoveredTargets_OUT
title: "_ReportDiscoveredTargets_OUT"
author: windows-driver-content
description: The ReportDiscoveredTargets_OUT structure holds the output data for the ReportDiscoveredTargets method.
old-location: storage\reportdiscoveredtargets_out.htm
old-project: storage
ms.assetid: cecef33a-a192-41f4-8006-b5d8b8c73e8d
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PReportDiscoveredTargets_OUT, PReportDiscoveredTargets_OUT, PReportDiscoveredTargets_OUT structure pointer [Storage Devices], ReportDiscoveredTargets_OUT, ReportDiscoveredTargets_OUT structure [Storage Devices], _ReportDiscoveredTargets_OUT, iscsifnd/PReportDiscoveredTargets_OUT, iscsifnd/ReportDiscoveredTargets_OUT, storage.reportdiscoveredtargets_out, structs-iSCSI_77e4d614-2993-45b7-8716-cc6eea197e22.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	ReportDiscoveredTargets_OUT
product: Windows
targetos: Windows
req.typenames: ReportDiscoveredTargets_OUT, *PReportDiscoveredTargets_OUT
---

# _ReportDiscoveredTargets_OUT structure


## -description


The ReportDiscoveredTargets_OUT structure holds the output data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564046">ReportDiscoveredTargets</a> method.


## -struct-fields




### -field Status

On output, the status of the <b>ReportDiscoveredTargets</b> operation. For a list of status qualifiers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>. 


### -field TargetCount

On output, the number of targets that are discovered. 


### -field Targets

On output, an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff561501">ISCSI_DiscoveredTarget</a> structures, which provide information that is related to discovered targets. 


## -remarks



You must implement this method.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561501">ISCSI_DiscoveredTarget</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564046">ReportDiscoveredTargets</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564054">ReportDiscoveredTargets2_OUT</a>
 

 


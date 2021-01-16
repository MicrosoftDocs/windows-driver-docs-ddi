---
UID: NS:iscsifnd._ReportDiscoveredTargets_OUT
title: _ReportDiscoveredTargets_OUT (iscsifnd.h)
description: The ReportDiscoveredTargets_OUT structure holds the output data for the ReportDiscoveredTargets method.
old-location: storage\reportdiscoveredtargets_out.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["ReportDiscoveredTargets_OUT structure"]
ms.keywords: "*PReportDiscoveredTargets_OUT, PReportDiscoveredTargets_OUT, PReportDiscoveredTargets_OUT structure pointer [Storage Devices], ReportDiscoveredTargets_OUT, ReportDiscoveredTargets_OUT structure [Storage Devices], _ReportDiscoveredTargets_OUT, iscsifnd/PReportDiscoveredTargets_OUT, iscsifnd/ReportDiscoveredTargets_OUT, storage.reportdiscoveredtargets_out, structs-iSCSI_77e4d614-2993-45b7-8716-cc6eea197e22.xml"
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
targetos: Windows
req.typenames: ReportDiscoveredTargets_OUT, *PReportDiscoveredTargets_OUT
f1_keywords:
 - _ReportDiscoveredTargets_OUT
 - iscsifnd/_ReportDiscoveredTargets_OUT
 - PReportDiscoveredTargets_OUT
 - iscsifnd/PReportDiscoveredTargets_OUT
 - ReportDiscoveredTargets_OUT
 - iscsifnd/ReportDiscoveredTargets_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iscsifnd.h
api_name:
 - _ReportDiscoveredTargets_OUT
 - PReportDiscoveredTargets_OUT
 - ReportDiscoveredTargets_OUT
---

# _ReportDiscoveredTargets_OUT structure


## -description

The ReportDiscoveredTargets_OUT structure holds the output data for the <a href="/windows-hardware/drivers/storage/reportdiscoveredtargets">ReportDiscoveredTargets</a> method.

## -struct-fields

### -field Status

On output, the status of the <b>ReportDiscoveredTargets</b> operation. For a list of status qualifiers, see <a href="/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>.

### -field TargetCount

On output, the number of targets that are discovered.

### -field Targets

On output, an array of <a href="/windows-hardware/drivers/ddi/iscsifnd/ns-iscsifnd-_iscsi_discoveredtarget">ISCSI_DiscoveredTarget</a> structures, which provide information that is related to discovered targets.

## -remarks

You must implement this method.

## -see-also

<a href="/windows-hardware/drivers/ddi/iscsifnd/ns-iscsifnd-_iscsi_discoveredtarget">ISCSI_DiscoveredTarget</a>



<a href="/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>



<a href="/windows-hardware/drivers/storage/reportdiscoveredtargets">ReportDiscoveredTargets</a>



<a href="/windows-hardware/drivers/ddi/iscsifnd/ns-iscsifnd-_reportdiscoveredtargets2_out">ReportDiscoveredTargets2_OUT</a>


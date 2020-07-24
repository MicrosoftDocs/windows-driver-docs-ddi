---
UID: NS:wdm._CLS_SCAN_CONTEXT
title: _CLS_SCAN_CONTEXT (wdm.h)
description: The CLFS_SCAN_CONTEXT structure holds context information to support a scan of the containers in a Common Log File System (CLFS) log.
old-location: kernel\clfs_scan_context.htm
tech.root: kernel
ms.assetid: 4f10abc6-1c86-4401-9af7-26d6c30f6fe8
ms.date: 04/30/2018
keywords: ["_CLS_SCAN_CONTEXT structure"]
ms.keywords: "*PCLFS_SCAN_CONTEXT, *PCLS_SCAN_CONTEXT, CLFS_SCAN_CONTEXT, CLFS_SCAN_CONTEXT structure [Kernel-Mode Driver Architecture], CLS_SCAN_CONTEXT, CLS_SCAN_CONTEXT structure [Kernel-Mode Driver Architecture], PCLFS_SCAN_CONTEXT, PCLFS_SCAN_CONTEXT structure pointer [Kernel-Mode Driver Architecture], PCLS_SCAN_CONTEXT, PCLS_SCAN_CONTEXT structure pointer [Kernel-Mode Driver Architecture], PPCLFS_SCAN_CONTEXT, PPCLFS_SCAN_CONTEXT structure pointer [Kernel-Mode Driver Architecture], PPCLS_SCAN_CONTEXT, PPCLS_SCAN_CONTEXT structure pointer [Kernel-Mode Driver Architecture], _CLS_SCAN_CONTEXT, kernel.clfs_scan_context, kstruct_a_286b1bd0-bd24-472c-be28-406269b7a687.xml, wdm/CLFS_SCAN_CONTEXT, wdm/CLS_SCAN_CONTEXT, wdm/PCLFS_SCAN_CONTEXT, wdm/PCLS_SCAN_CONTEXT, wdm/PPCLFS_SCAN_CONTEXT, wdm/PPCLS_SCAN_CONTEXT"
f1_keywords:
 - "wdm/CLS_SCAN_CONTEXT"
 - "CLS_SCAN_CONTEXT"
req.header: wdm.h
req.include-header: Wdm.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdm.h
api_name:
- CLS_SCAN_CONTEXT
targetos: Windows
req.typenames: CLS_SCAN_CONTEXT, *PCLS_SCAN_CONTEXT, PPCLS_SCAN_CONTEXT
---

# _CLS_SCAN_CONTEXT structure


## -description


The <b>CLFS_SCAN_CONTEXT</b> structure holds context information to support a scan of the containers in a Common Log File System (CLFS) log. The client allocates this structure by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfscreatescancontext">ClfsCreateScanContext</a>. Then, the client passes the structure repeatedly to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsscanlogcontainers">ClfsScanLogContainers</a>. 


## -struct-fields




### -field cidNode

A <a href="https://docs.microsoft.com/windows/desktop/api/clfs/ns-clfs-_clfs_node_id">CLFS_NODE_ID</a> structure that contains the scan context's node identity and type.


### -field plfoLog

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">LOG_FILE_OBJECT</a> structure that represents a CLFS log.


### -field cIndex

The index of the current container.


### -field cContainers

The number of containers to scan in each call to <b>ClfsScanLogContainers</b>. This is the number of elements in the array pointed to by <i>pinfoContainer</i>.


### -field cContainersReturned

The number of containers actually scanned in a call to <b>ClfsScanLogContainers</b>.


### -field eScanMode

This member can be one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
CLFS_SCAN_INIT

</td>
<td>
The scan is reinitialized and begins at the first container in the container list.

</td>
</tr>
<tr>
<td>
CLFS_SCAN_FORWARD

</td>
<td>
The next set of containers is scanned.

</td>
</tr>
<tr>
<td>
CLFS_SCAN_BACKWARD

</td>
<td>
The previous set of containers is scanned.

</td>
</tr>
<tr>
<td>
CLFS_SCAN_CLOSE

</td>
<td>
The scan is closed. No containers are scanned.

</td>
</tr>
</table>
 


### -field pinfoContainer

A pointer to an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cls_container_information">CLFS_CONTAINER_INFORMATION</a> structures. The <i>cContainers</i> parameter specifies the number of elements in this array. 


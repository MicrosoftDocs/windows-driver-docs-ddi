---
UID: NS:wdm._CLS_SCAN_CONTEXT
title: "_CLS_SCAN_CONTEXT"
author: windows-driver-content
description: The CLFS_SCAN_CONTEXT structure holds context information to support a scan of the containers in a Common Log File System (CLFS) log.
old-location: kernel\clfs_scan_context.htm
old-project: kernel
ms.assetid: 4f10abc6-1c86-4401-9af7-26d6c30f6fe8
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PCLFS_SCAN_CONTEXT, *PCLS_SCAN_CONTEXT, CLFS_SCAN_CONTEXT, CLFS_SCAN_CONTEXT structure [Kernel-Mode Driver Architecture], CLS_SCAN_CONTEXT, CLS_SCAN_CONTEXT structure [Kernel-Mode Driver Architecture], PCLFS_SCAN_CONTEXT, PCLFS_SCAN_CONTEXT structure pointer [Kernel-Mode Driver Architecture], PCLS_SCAN_CONTEXT, PCLS_SCAN_CONTEXT structure pointer [Kernel-Mode Driver Architecture], PPCLFS_SCAN_CONTEXT, PPCLFS_SCAN_CONTEXT structure pointer [Kernel-Mode Driver Architecture], PPCLS_SCAN_CONTEXT, PPCLS_SCAN_CONTEXT structure pointer [Kernel-Mode Driver Architecture], _CLS_SCAN_CONTEXT, kernel.clfs_scan_context, kstruct_a_286b1bd0-bd24-472c-be28-406269b7a687.xml, wdm/CLFS_SCAN_CONTEXT, wdm/CLS_SCAN_CONTEXT, wdm/PCLFS_SCAN_CONTEXT, wdm/PCLS_SCAN_CONTEXT, wdm/PPCLFS_SCAN_CONTEXT, wdm/PPCLS_SCAN_CONTEXT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	CLS_SCAN_CONTEXT
product: Windows
targetos: Windows
req.typenames: CLS_SCAN_CONTEXT, *PCLS_SCAN_CONTEXT, PPCLS_SCAN_CONTEXT
req.product: Windows 10 or later.
---

# _CLS_SCAN_CONTEXT structure


## -description


The <b>CLFS_SCAN_CONTEXT</b> structure holds context information to support a scan of the containers in a Common Log File System (CLFS) log. The client allocates this structure by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff541527">ClfsCreateScanContext</a>. Then, the client passes the structure repeatedly to <a href="https://msdn.microsoft.com/library/windows/hardware/ff541737">ClfsScanLogContainers</a>. 


## -struct-fields




### -field cidNode

A <a href="https://msdn.microsoft.com/99132138-b7ba-47a1-ac40-353d5d70db42">CLFS_NODE_ID</a> structure that contains the scan context's node identity and type.


### -field plfoLog

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554316">LOG_FILE_OBJECT</a> structure that represents a CLFS log.


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

A pointer to an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff541782">CLFS_CONTAINER_INFORMATION</a> structures. The <i>cContainers</i> parameter specifies the number of elements in this array. 


---
UID: NS:d3dkmddi._DXGKARG_QUERYDEPENDENTENGINEGROUP
title: "_DXGKARG_QUERYDEPENDENTENGINEGROUP"
author: windows-driver-content
description: Describes all nodes on the physical display adapter (engine) that are to be queried when the display port driver's GPU scheduler calls the DxgkDdiQueryDependentEngineGroup function to query node dependencies.
old-location: display\dxgkarg_querydependentenginegroup.htm
old-project: display
ms.assetid: 6b1d6465-83bd-42c4-be1f-d7a2cfb74483
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: DXGKARG_QUERYDEPENDENTENGINEGROUP, DXGKARG_QUERYDEPENDENTENGINEGROUP structure [Display Devices], _DXGKARG_QUERYDEPENDENTENGINEGROUP, d3dkmddi/DXGKARG_QUERYDEPENDENTENGINEGROUP, display.dxgkarg_querydependentenginegroup, *INOUT_DXGKARG_QUERYDEPENDENTENGINEGROUP
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3dkmddi.h
apiname:
-	DXGKARG_QUERYDEPENDENTENGINEGROUP
product: Windows
targetos: Windows
req.typenames: DXGKARG_QUERYDEPENDENTENGINEGROUP
---

# _DXGKARG_QUERYDEPENDENTENGINEGROUP structure


## -description


Describes all nodes on the physical display adapter (engine) that are to be queried when the display port driver's GPU scheduler calls the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_querydependentenginegroup.md">DxgkDdiQueryDependentEngineGroup</a> function to query node dependencies.


## -syntax


````
typedef struct _DXGKARG_QUERYDEPENDENTENGINEGROUP {
  UINT      NodeOrdinal;
  UINT      EngineOrdinal;
  ULONGLONG DependentNodeOrdinalMask;
} DXGKARG_QUERYDEPENDENTENGINEGROUP;
````


## -struct-fields




### -field NodeOrdinal

[in] An index of a node within the physical adapter defined by   the <b>EngineOrdinal</b> member that is being queried in a call to <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_querydependentenginegroup.md">DxgkDdiQueryDependentEngineGroup</a>.


### -field EngineOrdinal

[in] An index that defines the physical adapter in a linked display adapter (LDA) configuration that the node defined by <b>NodeOrdinal</b> belongs to.


### -field DependentNodeOrdinalMask

[out] The bitmask that describes all dependent nodes that will be affected by a reset operation.


## -remarks



The index value <b>EngineOrdinal</b> is assumed to be identical for all dependent nodes.

See Remarks of  <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_querydependentenginegroup.md">DxgkDdiQueryDependentEngineGroup</a> for a discussion of how to compute the bitmask in the <b>DependentNodeOrdinalMask</b> member.

For more information, see <a href="https://msdn.microsoft.com/5BC4F94C-2B45-44E2-8BBF-B455BB864A29">TDR changes in Windows 8</a>.




## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_querydependentenginegroup.md">DxgkDdiQueryDependentEngineGroup</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_resetengine.md">DxgkDdiResetEngine</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_QUERYDEPENDENTENGINEGROUP structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


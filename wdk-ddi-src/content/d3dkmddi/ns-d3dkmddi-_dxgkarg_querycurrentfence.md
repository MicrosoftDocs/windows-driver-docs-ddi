---
UID: NS:d3dkmddi._DXGKARG_QUERYCURRENTFENCE
title: "_DXGKARG_QUERYCURRENTFENCE"
author: windows-driver-content
description: The DXGKARG_QUERYCURRENTFENCE structure describes the latest completed submission fence.
old-location: display\dxgkarg_querycurrentfence.htm
old-project: display
ms.assetid: 84a7c49b-d079-4d14-b371-5cfb75c1331c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DmStructs_799a15e5-b780-43c4-a0c2-d97e3c91caec.xml, DXGKARG_QUERYCURRENTFENCE, *INOUT_PDXGKARG_QUERYCURRENTFENCE, d3dkmddi/DXGKARG_QUERYCURRENTFENCE, display.dxgkarg_querycurrentfence, DXGKARG_QUERYCURRENTFENCE structure [Display Devices], _DXGKARG_QUERYCURRENTFENCE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	d3dkmddi.h
apiname:
-	DXGKARG_QUERYCURRENTFENCE
product: Windows
targetos: Windows
req.typenames: DXGKARG_QUERYCURRENTFENCE
---

# _DXGKARG_QUERYCURRENTFENCE structure


## -description


The DXGKARG_QUERYCURRENTFENCE structure describes the latest completed submission fence. 


## -syntax


````
typedef struct _DXGKARG_QUERYCURRENTFENCE {
  UINT CurrentFence;
  UINT NodeOrdinal;
  UINT EngineOrdinal;
} DXGKARG_QUERYCURRENTFENCE;
````


## -struct-fields




### -field CurrentFence

[out] The current fence data.


### -field NodeOrdinal

[in] The zero-based index of the node for the current fence.


### -field EngineOrdinal

[in] The zero-based index of the engine, within the node that <b>NodeOrdinal</b> specifies, for the current fence.


## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_querycurrentfence.md">DxgkDdiQueryCurrentFence</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_QUERYCURRENTFENCE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


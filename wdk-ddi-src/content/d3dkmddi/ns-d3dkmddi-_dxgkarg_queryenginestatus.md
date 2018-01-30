---
UID: NS:d3dkmddi._DXGKARG_QUERYENGINESTATUS
title: "_DXGKARG_QUERYENGINESTATUS"
author: windows-driver-content
description: Used in a call to the DxgkDdiQueryEngineStatus function to specify a node within an active physical adapter (engine) that is to be queried for its progress.
old-location: display\dxgkarg_queryenginestatus.htm
old-project: display
ms.assetid: f7255c97-5c25-4ee2-988b-ff301878fe7c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmddi/DXGKARG_QUERYENGINESTATUS, _DXGKARG_QUERYENGINESTATUS, DXGKARG_QUERYENGINESTATUS structure [Display Devices], display.dxgkarg_queryenginestatus, DXGKARG_QUERYENGINESTATUS, *INOUT_PDXGKARG_QUERYENGINESTATUS
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
-	DXGKARG_QUERYENGINESTATUS
product: Windows
targetos: Windows
req.typenames: DXGKARG_QUERYENGINESTATUS
---

# _DXGKARG_QUERYENGINESTATUS structure


## -description


Used in a call to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryenginestatus.md">DxgkDdiQueryEngineStatus</a> function to specify a node within an active physical adapter (engine) that is to be queried for its progress.


## -syntax


````
typedef struct _DXGKARG_QUERYENGINESTATUS {
  UINT              NodeOrdinal;
  UINT              EngineOrdinal;
  DXGK_ENGINESTATUS EngineStatus;
} DXGKARG_QUERYENGINESTATUS;
````


## -struct-fields




### -field NodeOrdinal

[in] An index of a node within the physical adapter defined by   the <b>EngineOrdinal</b> member that is being queried in a call to <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryenginestatus.md">DxgkDdiQueryEngineStatus</a>.


### -field EngineOrdinal

[in] An index that defines the physical adapter in a linked display adapter (LDA) configuration that the node defined by <b>NodeOrdinal</b> belongs to.


### -field EngineStatus

[out] The progress, of type <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_enginestatus.md">DXGK_ENGINESTATUS</a>, of the node and physical adapter that are specified by the <b>NodeOrdinal</b> and <b>EngineOrdinal</b> members.


## -remarks


For more information, see <a href="https://msdn.microsoft.com/5BC4F94C-2B45-44E2-8BBF-B455BB864A29">TDR changes in Windows 8</a>.



## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_enginestatus.md">DXGK_ENGINESTATUS</a>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryenginestatus.md">DxgkDdiQueryEngineStatus</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_QUERYENGINESTATUS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


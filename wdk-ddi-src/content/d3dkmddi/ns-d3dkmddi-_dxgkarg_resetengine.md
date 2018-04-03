---
UID: NS:d3dkmddi._DXGKARG_RESETENGINE
title: "_DXGKARG_RESETENGINE"
author: windows-driver-content
description: Specifies a node within the physical display adapter that can be reset when the display port driver's GPU scheduler calls the DxgkDdiResetEngine function to request a reset operation.
old-location: display\dxgkarg_resetengine.htm
old-project: display
ms.assetid: a19eea7f-ceaf-47e0-b2dd-46511fcae66f
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*INOUT_PDXGKARG_RESETENGINE, DXGKARG_RESETENGINE, DXGKARG_RESETENGINE structure [Display Devices], _DXGKARG_RESETENGINE, d3dkmddi/DXGKARG_RESETENGINE, display.dxgkarg_resetengine"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dkmddi.h
api_name:
-	DXGKARG_RESETENGINE
product:
- Windows
targetos: Windows
req.typenames: DXGKARG_RESETENGINE
---

# _DXGKARG_RESETENGINE structure


## -description


Specifies a node within the physical display adapter that can be reset when the display port driver's GPU scheduler calls the <a href="https://msdn.microsoft.com/9c2097b2-5742-422c-a650-7efff2484970">DxgkDdiResetEngine</a> function to request a reset operation.


## -struct-fields




### -field NodeOrdinal

[in] An index of a node within the physical adapter defined by   the <b>EngineOrdinal</b> member that is being reset in a call to <a href="https://msdn.microsoft.com/9c2097b2-5742-422c-a650-7efff2484970">DxgkDdiResetEngine</a>.


### -field EngineOrdinal

[in] An index that defines the physical adapter in a linked display adapter (LDA) configuration that the node defined by <b>NodeOrdinal</b> belongs to.


### -field LastAbortedFenceId

[out] The fence identifier for the last packet that was aborted in the middle of execution.


## -remarks



For more information, see <a href="https://msdn.microsoft.com/5BC4F94C-2B45-44E2-8BBF-B455BB864A29">TDR changes in Windows 8</a>.




## -see-also




<a href="https://msdn.microsoft.com/9c2097b2-5742-422c-a650-7efff2484970">DxgkDdiResetEngine</a>
 

 


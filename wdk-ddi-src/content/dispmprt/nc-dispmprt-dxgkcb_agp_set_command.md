---
UID: NC:dispmprt.DXGKCB_AGP_SET_COMMAND
title: DXGKCB_AGP_SET_COMMAND (dispmprt.h)
description: The AgpSetCommand function sets the AGP rate and specifies whether side band addressing and fast write transactions are enabled.
old-location: display\agpsetcommand.htm
tech.root: display
ms.assetid: 4440bc0f-01cb-4108-bfe8-9d5127777f00
ms.date: 05/10/2018
keywords: ["DXGKCB_AGP_SET_COMMAND callback function"]
ms.keywords: AgpSetCommand, AgpSetCommand callback function [Display Devices], DXGKCB_AGP_SET_COMMAND, DXGKCB_AGP_SET_COMMAND callback, DpFunctions_7b0574a7-3c70-41e5-b7e7-908a86c2bccd.xml, display.agpsetcommand, dispmprt/AgpSetCommand
f1_keywords:
 - "dispmprt/AgpSetCommand"
 - "AgpSetCommand"
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- dispmprt.h
api_name:
- AgpSetCommand
targetos: Windows
req.typenames: 
---

# DXGKCB_AGP_SET_COMMAND callback function


## -description


The <b>AgpSetCommand</b> function sets the AGP rate and specifies whether side band addressing and fast write transactions are enabled.


## -parameters




### -param Context [in]

A handle to a context block that is associated with an AGP interface. The display miniport driver previously received this handle in the <b>Context</b> member of the DXGK_AGP_INTERFACE structure that was filled in by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkcb_query_services">DxgkCbQueryServices</a>.


### -param Command [in]

A set of flags that specify the AGP rate and the types of AGP transactions that will be used.

The caller must set one, and only one, of the following flags.

| **Flag** | **Meaning** | 
|:--|:--|
| DXGK_AGPCOMMAND_AGP1X | The AGP transfer rate is 1X. | 
| DXGK_AGPCOMMAND_AGP2X | The AGP transfer rate is 2X. | 
| DXGK_AGPCOMMAND_AGP4X | The AGP transfer rate is 4X. | 
| DXGK_AGPCOMMAND_AGP8X | The AGP transfer rate is 8X. | 


The caller might also choose to set or clear the following flags.

| **Flag** | **Meaning** | 
|:--|:--|
| DXGK_AGPCOMMAND_DISABLE_SBA | If this flag is set, side band addressing is disabled. If this flag is cleared, side band addressing is enabled. | 
| DXGK_AGPCOMMAND_DISABLE_FW | If this flag is set, fast write transactions are disabled. If this flag is cleared, fast write transactions are enabled. Note that fast write transactions cannot be used with AGP1X. | 



## -returns



<b>AgpSetCommand</b> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.


## -remarks



None.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkcb_agp_allocate_pool">AgpAllocatePool</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkcb_agp_free_pool">AgpFreePool</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_agp_interface">DXGK_AGP_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkcb_query_services">DxgkCbQueryServices</a>
 

 


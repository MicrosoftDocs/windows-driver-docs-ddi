---
UID: NC:dispmprt.DXGKCB_AGP_SET_COMMAND
title: DXGKCB_AGP_SET_COMMAND
author: windows-driver-content
description: The AgpSetCommand function sets the AGP rate and specifies whether side band addressing and fast write transactions are enabled.
old-location: display\agpsetcommand.htm
old-project: display
ms.assetid: 4440bc0f-01cb-4108-bfe8-9d5127777f00
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: AgpSetCommand, AgpSetCommand callback function [Display Devices], DXGKCB_AGP_SET_COMMAND, DpFunctions_7b0574a7-3c70-41e5-b7e7-908a86c2bccd.xml, display.agpsetcommand, dispmprt/AgpSetCommand
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	dispmprt.h
api_name:
-	AgpSetCommand
product: Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---

# DXGKCB_AGP_SET_COMMAND callback


## -description


The <b>AgpSetCommand</b> function sets the AGP rate and specifies whether side band addressing and fast write transactions are enabled.


## -parameters




### -param Context [in]

A handle to a context block that is associated with an AGP interface. The display miniport driver previously received this handle in the <b>Context</b> member of the DXGK_AGP_INTERFACE structure that was filled in by <a href="https://msdn.microsoft.com/0ce5df90-2019-4a92-97d6-0218acc8b1e8">DxgkCbQueryServices</a>.


### -param Command [in]

A set of flags that specify the AGP rate and the types of AGP transactions that will be used.

The caller must set one, and only one, of the following flags.

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
DXGK_AGPCOMMAND_AGP1X

</td>
<td>
The AGP transfer rate is 1X.

</td>
</tr>
<tr>
<td>
DXGK_AGPCOMMAND_AGP2X

</td>
<td>
The AGP transfer rate is 2X.

</td>
</tr>
<tr>
<td>
DXGK_AGPCOMMAND_AGP4X

</td>
<td>
The AGP transfer rate is 4X.

</td>
</tr>
<tr>
<td>
DXGK_AGPCOMMAND_AGP8X

</td>
<td>
The AGP transfer rate is 8X.

</td>
</tr>
</table>
 

The caller might also choose to set or clear the following flags.

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
DXGK_AGPCOMMAND_DISABLE_SBA

</td>
<td>
If this flag is set, side band addressing is disabled. If this flag is cleared, side band addressing is enabled.

</td>
</tr>
<tr>
<td>
DXGK_AGPCOMMAND_DISABLE_FW

</td>
<td>
If this flag is set, fast write transactions are disabled. If this flag is cleared, fast write transactions are enabled. Note that fast write transactions cannot be used with AGP1X.

</td>
</tr>
</table>
 


## -returns



<b>AgpSetCommand</b> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.




## -remarks



None.




## -see-also




<a href="https://msdn.microsoft.com/abac76e0-eb8a-450a-a797-3733a8f71990">AgpAllocatePool</a>



<a href="https://msdn.microsoft.com/6d4e957e-ad9c-45da-8d1d-0ef5f108c692">AgpFreePool</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560949">DXGK_AGP_INTERFACE</a>



<a href="https://msdn.microsoft.com/0ce5df90-2019-4a92-97d6-0218acc8b1e8">DxgkCbQueryServices</a>
 

 


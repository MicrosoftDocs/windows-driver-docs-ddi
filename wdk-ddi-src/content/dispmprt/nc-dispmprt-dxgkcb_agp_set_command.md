---
UID: NC:dispmprt.DXGKCB_AGP_SET_COMMAND
title: DXGKCB_AGP_SET_COMMAND
author: windows-driver-content
description: The AgpSetCommand function sets the AGP rate and specifies whether side band addressing and fast write transactions are enabled.
old-location: display\agpsetcommand.htm
old-project: display
ms.assetid: 4440bc0f-01cb-4108-bfe8-9d5127777f00
ms.author: windowsdriverdev
ms.date: 2/24/2018
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	dispmprt.h
apiname:
-	AgpSetCommand
product: Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---

# DXGKCB_AGP_SET_COMMAND callback


## -description


The <b>AgpSetCommand</b> function sets the AGP rate and specifies whether side band addressing and fast write transactions are enabled.


## -prototype


````
DXGKCB_AGP_SET_COMMAND AgpSetCommand;

NTSTATUS APIENTRY AgpSetCommand(
  _In_ HANDLE Context,
  _In_ ULONG  Command
)
{ ... }
````


## -parameters




### -param Context [in]

A handle to a context block that is associated with an AGP interface. The display miniport driver previously received this handle in the <b>Context</b> member of the DXGK_AGP_INTERFACE structure that was filled in by <a href="..\dispmprt\nc-dispmprt-dxgkcb_query_services.md">DxgkCbQueryServices</a>.


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

<a href="..\dispmprt\ns-dispmprt-_dxgk_agp_interface.md">DXGK_AGP_INTERFACE</a>



<a href="..\dispmprt\nc-dispmprt-dxgkcb_agp_allocate_pool.md">AgpAllocatePool</a>



<a href="..\dispmprt\nc-dispmprt-dxgkcb_agp_free_pool.md">AgpFreePool</a>



<a href="..\dispmprt\nc-dispmprt-dxgkcb_query_services.md">DxgkCbQueryServices</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_AGP_SET_COMMAND callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


---
UID: NC:dispmprt.DXGKDDI_MIRACAST_CREATE_CONTEXT
title: DXGKDDI_MIRACAST_CREATE_CONTEXT
author: windows-driver-content
description: Creates a kernel-mode context for a Miracast device.
old-location: display\dxgkddimiracastcreatecontext.htm
old-project: display
ms.assetid: BFF952CE-AA0F-4622-BBFC-946A45859FB7
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkddimiracastcreatecontext, DxgkDdiMiracastCreateContext callback function [Display Devices], DxgkDdiMiracastCreateContext, DXGKDDI_MIRACAST_CREATE_CONTEXT, DXGKDDI_MIRACAST_CREATE_CONTEXT, dispmprt/DxgkDdiMiracastCreateContext
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	Dispmprt.h
apiname:
-	DxgkDdiMiracastCreateContext
product: Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---

# DXGKDDI_MIRACAST_CREATE_CONTEXT callback


## -description


Creates a kernel-mode context for a Miracast device.


## -prototype


````
DXGKDDI_MIRACAST_CREATE_CONTEXT DxgkDdiMiracastCreateContext;

NTSTATUS* DxgkDdiMiracastCreateContext(
  _In_  PVOID                           DriverContext,
  _In_  DXGK_MIRACAST_DISPLAY_CALLBACKS *MiracastCallbacks,
  _Out_ PVOID                           *MiracastContext,
  _Out_ ULONG                           *TargetId
)
{ ... }
````


## -parameters




### -param DriverContext [in]

A handle to a context block that is associated with a display adapter. The display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.


### -param *MiracastCallbacks [in]

A pointer to an operating system-provided buffer that holds a <a href="..\dispmprt\ns-dispmprt-_dxgk_miracast_display_callbacks.md">DXGK_MIRACAST_DISPLAY_CALLBACKS</a> structure that has pointers to callback functions that the driver can call.


### -param *MiracastContext [out]

A pointer to an operating system-provided buffer that holds the address of the context that the driver allocated for this Miracast device instance.


### -param *TargetId [out]

A pointer to an operating system-provided buffer that holds the  ID of the VidPN target that the Miracast device is connected to. The driver should report this target as type <b>D3DKMDT_VOT_MIRACAST</b> when the operating system calls the <a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_relations.md">DxgkDdiQueryChildRelations</a> function during device initialization.


## -returns



Returns <b>STATUS_SUCCESS</b> if it succeeds. Otherwise, it returns one of the error codes that are defined in Ntstatus.h, including:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_RESOURCE_IN_USE</b></dt>
</dl>
</td>
<td width="60%">
The hardware resources needed to support a Miracast connected session aren't currently available.

</td>
</tr>
</table>
 




## -remarks



When this function is called, the display miniport driver should prepare all kernel-mode resources that it needs to support a Miracast connected session.

<h3><a id="Synchronization"></a><a id="synchronization"></a><a id="SYNCHRONIZATION"></a>Synchronization</h3>
The operating system groups the <i>DxgkDdiMiracastCreateContext</i>, <a href="..\dispmprt\nc-dispmprt-dxgkddi_miracast_destroy_context.md">DxgkDdiMiracastDestroyContext</a>, and <a href="..\dispmprt\nc-dispmprt-dxgkddi_miracast_handle_io_control.md">DxgkDdiMiracastIoControl</a> functions as a <i>Miracast</i> class. The operating system guarantees that these functions follow the second-level synchronization mode as defined in <a href="https://msdn.microsoft.com/2b7c1eae-6527-469e-a2fa-74d2a1246bd3">Threading and Synchronization Second Level</a>. These functions can be called when other level 0, 1, or other classes of level 2 functions are being called on another thread context. However, only one of these level 2 Miracast-class functions can be called at a time.




## -see-also

<a href="..\dispmprt\ns-dispmprt-_dxgk_miracast_display_callbacks.md">DXGK_MIRACAST_DISPLAY_CALLBACKS</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_relations.md">DxgkDdiQueryChildRelations</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_MIRACAST_CREATE_CONTEXT callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


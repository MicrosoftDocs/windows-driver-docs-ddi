---
UID: NS:d3dkmthk._D3DKMT_POLLDISPLAYCHILDREN
title: _D3DKMT_POLLDISPLAYCHILDREN
author: windows-driver-content
description: The D3DKMT_POLLDISPLAYCHILDREN structure describes parameters for querying for connectivity status of all child devices of the given display adapter.
old-location: display\d3dkmt_polldisplaychildren.htm
old-project: display
ms.assetid: 39d62c39-a892-4ccd-aea6-32d102d1891c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DKMT_POLLDISPLAYCHILDREN, D3DKMT_POLLDISPLAYCHILDREN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_POLLDISPLAYCHILDREN
req.alt-loc: d3dkmthk.h
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
req.typenames: D3DKMT_POLLDISPLAYCHILDREN
---

# _D3DKMT_POLLDISPLAYCHILDREN structure



## -description
The D3DKMT_POLLDISPLAYCHILDREN structure describes parameters for querying for connectivity status of all child devices of the given display adapter.



## -syntax

````
typedef struct _D3DKMT_POLLDISPLAYCHILDREN {
  D3DKMT_HANDLE hAdapter;
  UINT          NonDestructiveOnly;
  UINT          SynchronousPolling;
  UINT          DisableModeReset;
  UINT          PollAllAdapters;
  UINT          PollInterruptible;
  UINT          Reserved;
} D3DKMT_POLLDISPLAYCHILDREN;
````


## -struct-fields

### -field hAdapter

[in] A D3DKMT_HANDLE data type that represents the kernel-mode handle to the graphics adapter to query for connectivity status of child devices.


### -field NonDestructiveOnly

[in] A UINT value that specifies whether the call to the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtpolldisplaychildren.md">D3DKMTPollDisplayChildren</a> function should be only nondestructive. A nonzero value indicates only a nondestructive call; a zero value indicates the call can be destructive (that is, the call can cause visual artifacts on the screen). 


### -field SynchronousPolling

Supported beginning with Windows 7 operating system.

[in] A UINT value that specifies whether the connectivity status of all child devices is reported within 1 second of the call to <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtpolldisplaychildren.md">D3DKMTPollDisplayChildren</a>. If set to a nonzero value, connectivity status is reported within 1 second. Otherwise, there is no time limit on when the display miniport can complete and report the polling.

If the display miniport driver needs to poll child devices after receiving notice of an ACPI event, the runtime should set <b>SynchronousPolling</b> to a nonzero value.


### -field DisableModeReset

Supported beginning with Windows 7 operating system.

[in] A UINT value that specifies whether any reactions of the display miniport driver to discoveries of new child devices are disabled during the polling interval. If set to a nonzero value, such reactions of the driver are disabled during the polling interval. In this case, set the <b>SynchronousPolling</b>parameter when setting <b>DisableModeReset</b>. Otherwise, normal reactions of the driver to discoveries of new child devices are allowed.


### -field PollAllAdapters

Supported beginning with Windows 7 operating system.

[in] A UINT value that specifies whether all child devices are polled. If set to a nonzero value, all child devices are polled. Otherwise, only the child devices that are on the specified adapter are discovered in the polling.


### -field PollInterruptible

Supported beginning with Windows 7 operating system.

[in] A UINT value that specifies whether child devices that are aware of hot-plug detection (HPD) are polled. If set to a nonzero value, HPD-aware child devices are polled. Otherwise, HPD-aware child devices might not be discovered in the polling.

HPD-aware devices are those for which, in a call to <a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_relations.md">DxgkDdiQueryChildRelations</a>, the <b>ChildRelations</b>.<b>ChildCapabilities</b>.<b>HpdAwareness</b> member has a value not equal to HpdAwarenessUninitialized or HpdAwarenessNone.

For more information on HPD-aware devices, see <a href="https://msdn.microsoft.com/170d2d5d-fd46-431d-9672-61fa048f7dd2">Monitor Hot Plug Detection</a>.


### -field Reserved

Supported beginning with Windows 7 operating system.

[in] This member is reserved and should be set to zero. Setting this member is equivalent to setting the remaining 26 bits (0xFFFFFFC0) of a 32-bit value to zeros.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtpolldisplaychildren.md">D3DKMTPollDisplayChildren</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_relations.md">DxgkDdiQueryChildRelations</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_POLLDISPLAYCHILDREN structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


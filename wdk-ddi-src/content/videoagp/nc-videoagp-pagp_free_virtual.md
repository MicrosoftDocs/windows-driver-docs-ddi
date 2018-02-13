---
UID: NC:videoagp.PAGP_FREE_VIRTUAL
title: PAGP_FREE_VIRTUAL
author: windows-driver-content
description: The AgpFreeVirtual function frees virtual memory committed by a previous call to AgpCommitVirtual.
old-location: display\agpfreevirtual.htm
old-project: display
ms.assetid: a6f689ab-8cf1-4207-af2b-30957500c190
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.agpfreevirtual, AgpFreeVirtual callback function [Display Devices], AgpFreeVirtual, PAGP_FREE_VIRTUAL, PAGP_FREE_VIRTUAL, videoagp/AgpFreeVirtual, VideoPort_Functions_49eabd30-2590-466f-b9d4-f2577a7e78e4.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: videoagp.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
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
-	videoagp.h
apiname:
-	AgpFreeVirtual
product: Windows
targetos: Windows
req.typenames: VP_SCATTER_GATHER_LIST, *PVP_SCATTER_GATHER_LIST
req.product: Windows 10 or later.
---

# PAGP_FREE_VIRTUAL callback


## -description


The <b>AgpFreeVirtual</b> function frees virtual memory committed by a previous call to <a href="..\videoagp\nc-videoagp-pagp_commit_virtual.md">AgpCommitVirtual</a>.


## -prototype


````
PAGP_FREE_VIRTUAL AgpFreeVirtual;

VOID APIENTRY AgpFreeVirtual(
  _In_ PVOID HwDeviceExtension,
  _In_ PVOID VirtualReserveContext,
  _In_ ULONG Pages,
  _In_ ULONG Offset
)
{ ... }
````


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param VirtualReserveContext [in]

Identifies a reserved virtual address range. This context handle was obtained from <a href="..\videoagp\nc-videoagp-pagp_reserve_virtual.md">AgpReserveVirtual</a>.


### -param Pages [in]

Specifies the number of pages of virtual memory that the video port driver should unmap.


### -param Offset [in]

Specifies the page offset into the reserved virtual address range identified by <b>VirtualReserveContext</b> that indicates the actual base address at which to unmap virtual memory.


## -returns



None




## -remarks



When a miniport driver calls <b>AgpFreeVirtual</b>, <i>Pages</i> pages of virtual addresses are unmapped. The unmapped range begins <b>Offset</b> pages into the range associated with <b>VirtualReserveContext</b>. The miniport driver must specify that the exact offset and number of pages be freed as were committed in a prior call to <a href="..\videoagp\nc-videoagp-pagp_commit_virtual.md">AgpCommitVirtual</a>. 

A call to <b>AgpFreeVirtual</b> must be paired with a previous call to <a href="..\videoagp\nc-videoagp-pagp_commit_virtual.md">AgpCommitVirtual</a>, and that call to <b>AgpCommitVirtual</b> must be preceded by a successful call to <a href="..\videoagp\nc-videoagp-pagp_reserve_virtual.md">AgpReserveVirtual</a>. If <b>AgpReserveVirtual</b> fails (returns <b>NULL</b>), you must not call <b>AgpCommitVirtual</b> or <b>AgpFreeVirtual</b>. 




## -see-also

<a href="..\videoagp\nc-videoagp-pagp_commit_virtual.md">AgpCommitVirtual</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PAGP_FREE_VIRTUAL callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


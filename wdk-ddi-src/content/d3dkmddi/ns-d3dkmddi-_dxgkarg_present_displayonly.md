---
UID: NS:d3dkmddi._DXGKARG_PRESENT_DISPLAYONLY
title: "_DXGKARG_PRESENT_DISPLAYONLY"
author: windows-driver-content
description: Indicates how a kernel mode display-only driver (KMDOD) is to perform a present operation.
old-location: display\dxgkarg_present_displayonly.htm
old-project: display
ms.assetid: 7679d4f2-55c6-458c-afd3-020c3b7fd7e2
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGKARG_PRESENT_DISPLAYONLY, display.dxgkarg_present_displayonly, d3dkmddi/DXGKARG_PRESENT_DISPLAYONLY, DXGKARG_PRESENT_DISPLAYONLY structure [Display Devices], _DXGKARG_PRESENT_DISPLAYONLY
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
-	DXGKARG_PRESENT_DISPLAYONLY
product: Windows
targetos: Windows
req.typenames: DXGKARG_PRESENT_DISPLAYONLY
---

# _DXGKARG_PRESENT_DISPLAYONLY structure


## -description


Indicates how a kernel mode display-only driver (KMDOD) is to perform a present operation.


## -syntax


````
typedef struct _DXGKARG_PRESENT_DISPLAYONLY {
  D3DDDI_VIDEO_PRESENT_SOURCE_ID      VidPnSourceId;
  VOID                                *pSource;
  ULONG                               BytesPerPixel;
  LONG                                Pitch;
  D3DKMT_PRESENT_DISPLAY_ONLY_FLAGS   Flags;
  ULONG                               NumMoves;
  D3DKMT_MOVE_RECT                    *pMoves;
  ULONG                               NumDirtyRects;
  RECT                                *pDirtyRect;
  DXGKCB_PRESENT_DISPLAYONLY_PROGRESS pfnPresentDisplayOnlyProgress;
} DXGKARG_PRESENT_DISPLAYONLY;
````


## -struct-fields




#### - VidPnSourceId

The zero-based identification number of the video present source in a path of a video present network (VidPN) topology on which to restrict displaying.


#### - pSource

The virtual start address of the source image.


#### - BytesPerPixel

The number of bytes per pixel in the source image.


#### - Pitch

The pitch, in bytes, of each line in the source image—that is, the distance, in bytes, to the start of the next line.


#### - Flags

A <a href="..\d3dkmddi\ns-d3dkmddi-_d3dkmt_present_display_only_flags.md">D3DKMT_PRESENT_DISPLAY_ONLY_FLAGS</a> structure that identifies how to display the source image in the present operation.


#### - NumMoves

The number of screen-to-screen moves that are pointed to by the <b>pMoves</b> member.


#### - pMoves

A pointer to a list of <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmt_move_rect.md">D3DKMT_MOVE_RECT</a> screen-to-screen moves.


#### - NumDirtyRects

The number of dirty rectangles that are pointed to by the <b>pDirtyRect</b> member.


#### - pDirtyRect

A pointer to a list of <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> dirty rectangles.


#### - pfnPresentDisplayOnlyProgress

Reserved for system use. The operating system sets this member to <b>NULL</b>.


## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_d3dkmt_present_display_only_flags.md">D3DKMT_PRESENT_DISPLAY_ONLY_FLAGS</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>

<a href="https://msdn.microsoft.com/8970246b-b46f-464f-93b2-973cc351ed07">DxgkCbPresentDisplayOnlyProgress</a>

<a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmt_move_rect.md">D3DKMT_MOVE_RECT</a>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_presentdisplayonly.md">DxgkDdiPresentDisplayOnly</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_PRESENT_DISPLAYONLY structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


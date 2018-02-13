---
UID: NE:d3dkmddi._DXGK_PRESENT_DISPLAY_ONLY_PROGRESS_ID
title: "_DXGK_PRESENT_DISPLAY_ONLY_PROGRESS_ID"
author: windows-driver-content
description: Indicates the status of the current present operation.
old-location: display\dxgk_present_display_only_progress_id.htm
old-project: display
ms.assetid: 38023aaf-754a-4b16-96fc-6fd3d48233c3
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmddi/DXGK_PRESENT_DISPLAYONLY_PROGRESS_ID_COMPLETE, DXGK_PRESENT_DISPLAYONLY_PROGRESS_ID_COMPLETE, DXGK_PRESENT_DISPLAY_ONLY_PROGRESS_ID, d3dkmddi/DXGK_PRESENT_DISPLAY_ONLY_PROGRESS_ID, d3dkmddi/DXGK_PRESENT_DISPLAYONLY_PROGRESS_ID_FAILED, DXGK_PRESENT_DISPLAY_ONLY_PROGRESS_ID enumeration [Display Devices], _DXGK_PRESENT_DISPLAY_ONLY_PROGRESS_ID, display.dxgk_present_display_only_progress_id, DXGK_PRESENT_DISPLAYONLY_PROGRESS_ID_FAILED
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmddi.h
req.include-header: 
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
-	DXGK_PRESENT_DISPLAY_ONLY_PROGRESS_ID
product: Windows
targetos: Windows
req.typenames: DXGK_PRESENT_DISPLAY_ONLY_PROGRESS_ID
---

# _DXGK_PRESENT_DISPLAY_ONLY_PROGRESS_ID enumeration


## -description


Indicates the status of the current present operation.


## -syntax


````
typedef enum _DXGK_PRESENT_DISPLAY_ONLY_PROGRESS_ID { 
  DXGK_PRESENT_DISPLAYONLY_PROGRESS_ID_COMPLETE  = 0,
  DXGK_PRESENT_DISPLAYONLY_PROGRESS_ID_FAILED    = 1
} DXGK_PRESENT_DISPLAY_ONLY_PROGRESS_ID;
````


## -enum-fields




### -field DXGK_PRESENT_DISPLAYONLY_PROGRESS_ID_COMPLETE

The present operation has completed.


### -field DXGK_PRESENT_DISPLAYONLY_PROGRESS_ID_FAILED

An error occurred during the present operation.


## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkargcb_present_displayonly_progress.md">DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_PRESENT_DISPLAY_ONLY_PROGRESS_ID enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


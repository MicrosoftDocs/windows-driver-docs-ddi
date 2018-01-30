---
UID: NS:ntddvdeo._VIDEO_POINTER_POSITION
title: "_VIDEO_POINTER_POSITION"
author: windows-driver-content
description: The VIDEO_POINTER_POSITION structure contains the location of the screen pointer relative to the top left corner of the screen.
old-location: display\video_pointer_position.htm
old-project: display
ms.assetid: 07586be9-a8bc-4149-8037-7b649a75a818
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "_VIDEO_POINTER_POSITION, Video_Structs_72aeeda6-58eb-419e-95d2-35c1b66adf36.xml, VIDEO_POINTER_POSITION structure [Display Devices], PVIDEO_POINTER_POSITION, PVIDEO_POINTER_POSITION structure pointer [Display Devices], VIDEO_POINTER_POSITION, *PVIDEO_POINTER_POSITION, ntddvdeo/PVIDEO_POINTER_POSITION, ntddvdeo/VIDEO_POINTER_POSITION, display.video_pointer_position"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddvdeo.h
req.include-header: Ntddvdeo.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddvdeo.h
apiname:
-	VIDEO_POINTER_POSITION
product: Windows
targetos: Windows
req.typenames: VIDEO_POINTER_POSITION, *PVIDEO_POINTER_POSITION
---

# _VIDEO_POINTER_POSITION structure


## -description


The VIDEO_POINTER_POSITION structure contains the location of the screen pointer relative to the top left corner of the screen.


## -syntax


````
typedef struct _VIDEO_POINTER_ATTRIBUTES {
  SHORT Column;
  SHORT Row;
} VIDEO_POINTER_POSITION, *PVIDEO_POINTER_POSITION;
````


## -struct-fields




### -field Column

Specifies the column location of the pointer in pixels, starting from the top left corner of the screen.


### -field Row

Specifies the row location of the pointer in pixels, starting from the top left corner of the screen.


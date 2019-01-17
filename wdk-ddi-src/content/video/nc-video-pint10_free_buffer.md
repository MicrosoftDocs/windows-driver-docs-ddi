---
UID: NC:video.PINT10_FREE_BUFFER
title: PINT10_FREE_BUFFER
description: The Int10FreeBuffer function frees a buffer previously allocated by Int10AllocateBuffer.
old-location: display\int10freebuffer.htm
tech.root: display
ms.assetid: feb7dd98-8c44-405e-8e98-ffd6246cf0ee
ms.date: 05/10/2018
ms.keywords: Int10FreeBuffer, Int10FreeBuffer callback function [Display Devices], PINT10_FREE_BUFFER, PINT10_FREE_BUFFER callback, VideoPort_Functions_607fc1f2-1d9a-48eb-97c2-a2cd510e3d78.xml, display.int10freebuffer, video/Int10FreeBuffer
ms.topic: callback
req.header: video.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	video.h
api_name:
-	Int10FreeBuffer
product:
- Windows
targetos: Windows
req.typenames: 
---

# PINT10_FREE_BUFFER callback function


## -description


The <i>Int10FreeBuffer</i> function frees a buffer previously allocated by <i>Int10AllocateBuffer</i>.


## -parameters




### -param Context [in]

Pointer to a video port driver-defined context for the interface. This should be the same as the value in the <b>Context</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570539">VIDEO_PORT_INT10_INTERFACE</a> structure after <a href="https://msdn.microsoft.com/library/windows/hardware/ff570337">VideoPortQueryServices</a> returns.


### -param Seg [in]

Specifies the segment address of the buffer to be freed.


### -param Off [in]

Specifies the offset within the segment indicated by the <i>Seg</i> parameter.


## -returns



The <i>Int10FreeBuffer</i> function returns NO_ERROR upon success. Otherwise, the function returns an appropriate error code.




## -remarks



The video port implements this function, which can be accessed through a pointer in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570539">VIDEO_PORT_INT10_INTERFACE</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570539">VIDEO_PORT_INT10_INTERFACE</a>
 

 


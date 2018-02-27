---
UID: NF:d3dkmthk.D3DKMTCheckExclusiveOwnership
title: D3DKMTCheckExclusiveOwnership function
author: windows-driver-content
description: The D3DKMTCheckExclusiveOwnership function checks whether any kernel device object in the operating system has an exclusive level of ownership of any video present sources.
old-location: display\d3dkmtcheckexclusiveownership.htm
old-project: display
ms.assetid: 1695abc2-13ef-4168-b3f5-e9e8be55c5f0
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DKMTCheckExclusiveOwnership, D3DKMTCheckExclusiveOwnership callback function [Display Devices], OpenGL_Functions_f5c7a3e5-651c-48f0-b58c-4a6571c10a61.xml, PFND3DKMT_CHECKEXCLUSIVEOWNERSHIP, d3dkmthk/D3DKMTCheckExclusiveOwnership, display.d3dkmtcheckexclusiveownership
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	D3dkmthk.h
apiname:
-	D3DKMTCheckExclusiveOwnership
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTCheckExclusiveOwnership function


## -description


The <b>D3DKMTCheckExclusiveOwnership</b> function checks whether any kernel device object in the operating system has an exclusive level of ownership of any video present sources. 


## -syntax


````
BOOLEAN APIENTRY D3DKMTCheckExclusiveOwnership(
   void 
);
````


## -parameters








## -returns



<b>D3DKMTCheckExclusiveOwnership</b> returns a Boolean value that indicates <b>TRUE</b> if any kernel device object in the operating system has an exclusive level of ownership of any video present sources and <b>FALSE</b> otherwise. 




## -remarks



For a description of ownership levels of video present sources, see the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtsetvidpnsourceowner.md">D3DKMTSetVidPnSourceOwner</a> function and the <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_setvidpnsourceowner.md">D3DKMT_SETVIDPNSOURCEOWNER</a> structure. An exclusive level of ownership is represented by the D3DKMT_VIDPNSOURCEOWNER_EXCLUSIVE or D3DKMT_VIDPNSOURCEOWNER_EXCLUSIVEGDI owner type, which can be specified in one of the elements in the array that the <b>pType</b> member of D3DKMT_SETVIDPNSOURCEOWNER specifies.




## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtsetvidpnsourceowner.md">D3DKMTSetVidPnSourceOwner</a>



<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_setvidpnsourceowner.md">D3DKMT_SETVIDPNSOURCEOWNER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DKMT_CHECKEXCLUSIVEOWNERSHIP callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


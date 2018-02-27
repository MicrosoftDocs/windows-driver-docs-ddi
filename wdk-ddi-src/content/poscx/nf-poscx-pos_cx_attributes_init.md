---
UID: NF:poscx.POS_CX_ATTRIBUTES_INIT
title: POS_CX_ATTRIBUTES_INIT function
author: windows-driver-content
description: POS_CX_ATTRIBUTES_INIT initializes a POS_CX_ATTRIBUTE structure.
old-location: pos\pos_cx_attributes_init.htm
old-project: pos
ms.assetid: A1287386-E831-474A-858C-89787741FD57
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: POS_CX_ATTRIBUTES_INIT, POS_CX_ATTRIBUTES_INIT function, pos.pos_cx_attributes_init, poscx/POS_CX_ATTRIBUTES_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: poscx.h
req.include-header: Poscx.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	poscx.h
apiname:
-	POS_CX_ATTRIBUTES_INIT
product: Windows
targetos: Windows
req.typenames: POS_CX_EVENT_PRIORITY
req.product: Windows 10 or later.
---

# POS_CX_ATTRIBUTES_INIT function


## -description


POS_CX_ATTRIBUTES_INIT initializes a <a href="..\poscx\ns-poscx-_pos_cx_attributes.md">POS_CX_ATTRIBUTE</a> structure.


## -syntax


````
VOID POS_CX_ATTRIBUTES_INIT(
  _Out_ POS_CX_ATTRIBUTE *PosCxAttrPtr
);
````


## -parameters




### -param PosCxAttrPtr [out]

A pointer to the caller-allocated <a href="..\poscx\ns-poscx-_pos_cx_attributes.md">POS_CX_ATTRIBUTE</a> structure to initialize.


## -returns



This function does not return a value.




## -see-also

<a href="..\poscx\nf-poscx-poscxinit.md">PosCxInit</a>



<a href="..\poscx\ns-poscx-_pos_cx_attributes.md">POS_CX_ATTRIBUTE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [pos\pos]:%20POS_CX_ATTRIBUTES_INIT function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


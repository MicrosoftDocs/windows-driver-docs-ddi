---
UID: NS:iddcx.IDARG_IN_COMMITMODES
title: IDARG_IN_COMMITMODES
author: windows-driver-content
description: Gives information about the paths that need to be committed.
old-location: display\idarg_in_commitmodes.htm
old-project: display
ms.assetid: 242b7573-409a-4fdc-8ebf-596b8e6d41c7
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IDARG_IN_COMMITMODES, IDARG_IN_COMMITMODES structure [Display Devices], display.idarg_in_commitmodes, iddcx/IDARG_IN_COMMITMODES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iddcx.h
req.include-header: 
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
-	iddcx.h
apiname:
-	IDARG_IN_COMMITMODES
product: Windows
targetos: Windows
req.typenames: 
---

# IDARG_IN_COMMITMODES structure


## -description


Gives information about the paths that need to be committed.
             


## -syntax


````
typedef struct IDARG_IN_COMMITMODES {
  UINT                                PathCount;
  _Field_size_(PathCount) IDDCX_PATH* pPaths;
} IDARG_IN_COMMITMODES, *IDARG_IN_COMMITMODES;
````


## -struct-fields




### -field PathCount


                     [in] The number of paths in the <b>pPaths</b> array
                 


### -field pPaths


                     [in] A pointer to the array of paths that need to be committed.
                 


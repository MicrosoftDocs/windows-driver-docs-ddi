---
UID: NS:d3dkmddi._DXGK_ENGINESTATUS
title: "_DXGK_ENGINESTATUS"
author: windows-driver-content
description: Indicates the progress of a node within an active physical display adapter (engine) specified by a DXGKARG_QUERYENGINESTATUS structure.
old-location: display\dxgk_enginestatus.htm
old-project: display
ms.assetid: e052e3bc-688e-4aa8-b987-88ed6963774a
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGK_ENGINESTATUS structure [Display Devices], display.dxgk_enginestatus, d3dkmddi/DXGK_ENGINESTATUS, DXGK_ENGINESTATUS, _DXGK_ENGINESTATUS
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
-	DXGK_ENGINESTATUS
product: Windows
targetos: Windows
req.typenames: DXGK_ENGINESTATUS
---

# _DXGK_ENGINESTATUS structure


## -description


Indicates the progress of a node within an active physical display adapter (engine) specified by a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_queryenginestatus.md">DXGKARG_QUERYENGINESTATUS</a> structure.


## -syntax


````
typedef struct _DXGK_ENGINESTATUS {
  union {
    struct {
      UINT Responsive;
      UINT Reserved;
    };
    UINT   Value;
  };
} DXGK_ENGINESTATUS;
````


## -struct-fields




### -field Responsive

The display miniport driver must set this member to a value of 1 if the node and physical adapter are making progress in operations, or to 0 if the node and physical adapter are not responding to queries to report progress.


### -field Reserved

This member is reserved and should be set to zero.


### -field Value

A 32-bit value that specifies the progress of the physical adapter.


## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_queryenginestatus.md">DXGKARG_QUERYENGINESTATUS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_ENGINESTATUS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


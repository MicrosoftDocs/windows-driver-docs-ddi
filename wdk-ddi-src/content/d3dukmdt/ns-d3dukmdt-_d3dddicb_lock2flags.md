---
UID: NS:d3dukmdt._D3DDDICB_LOCK2FLAGS
title: "_D3DDDICB_LOCK2FLAGS"
author: windows-driver-content
description: D3DDDICB_LOCK2FLAGS is used by the Lock2 kernel function to determine how an allocation is locked.
old-location: display\d3dddicb_lock2flags.htm
old-project: display
ms.assetid: 1F802912-F99B-4C04-9ABD-8FCC50FD3859
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DDDICB_LOCK2FLAGS structure [Display Devices], D3DDDICB_LOCK2FLAGS, display.d3dddicb_lock2flags, d3dukmdt/D3DDDICB_LOCK2FLAGS, _D3DDDICB_LOCK2FLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	d3dukmdt.h
apiname:
-	D3DDDICB_LOCK2FLAGS
product: Windows
targetos: Windows
req.typenames: D3DDDICB_LOCK2FLAGS
---

# _D3DDDICB_LOCK2FLAGS structure


## -description


<b>D3DDDICB_LOCK2FLAGS</b> is used by the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtlock2.md">Lock2</a> kernel function to determine how an allocation is locked.
   
  Unlike <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtlock.md">Lock</a>, which supported numerous flags, <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtlock2.md">Lock2</a> has none. The <b>Lock2</b> arguments allow flags to be specified using this structure, but currently it only has a reserved field to allow for capabilities to added in the future.


## -syntax


````
typedef struct _D3DDDICB_LOCK2FLAGS {
  union {
    struct {
      UINT Reserved  :32;
    };
    UINT   Value;
  };
} D3DDDICB_LOCK2FLAGS;
````


## -struct-fields




### -field Reserved

This member is reserved and must be zero.


### -field Value

This member must be zero.


## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtlock2.md">Lock2</a>

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtlock.md">Lock</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_LOCK2FLAGS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


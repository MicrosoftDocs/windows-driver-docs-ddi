---
UID: NF:printoem.OEMQueryFontTree
title: OEMQueryFontTree function
author: windows-driver-content
description: The OEMQueryFontTree function provides GDI with a pointer to a structure that defines one of the following:
old-location: print\oemqueryfonttree.htm
old-project: print
ms.assetid: e2e30707-dffd-4990-a552-b67a7d9e2ca4
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: printoem/OEMQueryFontTree, print.oemqueryfonttree, print_unidrv-pscript_rendering_f069b851-3104-4cca-8902-d844350a719e.xml, OEMQueryFontTree function [Print Devices], OEMQueryFontTree
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: printoem.h
req.include-header: Printoem.h
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
-	printoem.h
apiname:
-	OEMQueryFontTree
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---

# OEMQueryFontTree function


## -description


The <code>OEMQueryFontTree</code> function provides GDI with a pointer to a structure that defines one of the following: 
<ul>
<li>
A mapping from Unicode to glyph handles, including glyph variants 

</li>
<li>
A mapping of kerning pairs to kerning handles

</li>
</ul>

## -syntax


````
PVOID APIENTRY OEMQueryFontTree(
   DHPDEV    dhpdev,
   ULONG_PTR iFile,
   ULONG     iFace,
   ULONG     iMode,
   ULONG_PTR *pid
);
````


## -parameters




### -param dhpdev


### -param iFile


### -param iFace


### -param iMode


### -param pid


---
UID: NF:printoem.OEMQueryFontTree
title: OEMQueryFontTree function (printoem.h)
description: The OEMQueryFontTree function provides GDI with a pointer to a structure that defines one of the following.
old-location: print\oemqueryfonttree.htm
tech.root: print
ms.assetid: e2e30707-dffd-4990-a552-b67a7d9e2ca4
ms.date: 04/20/2018
keywords: ["OEMQueryFontTree function"]
ms.keywords: OEMQueryFontTree, OEMQueryFontTree function [Print Devices], print.oemqueryfonttree, print_unidrv-pscript_rendering_f069b851-3104-4cca-8902-d844350a719e.xml, printoem/OEMQueryFontTree
f1_keywords:
 - "printoem/OEMQueryFontTree"
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- printoem.h
api_name:
- OEMQueryFontTree
product:
- Windows
targetos: Windows
req.typenames: 
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

## -parameters




### -param dhpdev


### -param iFile


### -param iFace


### -param iMode


### -param pid


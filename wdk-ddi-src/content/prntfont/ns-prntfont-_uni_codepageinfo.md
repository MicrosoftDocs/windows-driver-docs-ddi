---
UID: NS:prntfont._UNI_CODEPAGEINFO
title: _UNI_CODEPAGEINFO
author: windows-driver-content
description: The UNI_CODEPAGEINFO structure is one of the structures used to define the contents of glyph translation table files (.gtt files).
old-location: print\uni_codepageinfo.htm
old-project: print
ms.assetid: 042362d3-d5bf-47af-957f-8f1eb7a9ca7a
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: _UNI_CODEPAGEINFO, print_unidrv-pscript_fonts_63611a4f-c59c-4fee-a8f3-c1391ff02afd.xml, *PUNI_CODEPAGEINFO, prntfont/UNI_CODEPAGEINFO, PUNI_CODEPAGEINFO structure pointer [Print Devices], print.uni_codepageinfo, UNI_CODEPAGEINFO, prntfont/PUNI_CODEPAGEINFO, PUNI_CODEPAGEINFO, UNI_CODEPAGEINFO structure [Print Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: prntfont.h
req.include-header: Prntfont.h
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
-	prntfont.h
apiname: 
-	UNI_CODEPAGEINFO
product: Windows
targetos: Windows
req.typenames: UNI_CODEPAGEINFO, *PUNI_CODEPAGEINFO
req.product: Windows 10 or later.
---

# _UNI_CODEPAGEINFO structure


## -description


The UNI_CODEPAGEINFO structure is one of the structures used to define the contents of <a href="https://msdn.microsoft.com/6e643703-ace1-4660-990c-3a9ca735829d">glyph translation table files</a> (.gtt files).


## -syntax


````
typedef struct _UNI_CODEPAGEINFO {
  DWORD dwCodePage;
  INVOC SelectSymbolSet;
  INVOC UnSelectSymbolSet;
} UNI_CODEPAGEINFO, *PUNI_CODEPAGEINFO;
````


## -struct-fields




### -field dwCodePage

Identifies a Windows code page.


### -field SelectSymbolSet

Is an <a href="..\prntfont\ns-prntfont-_invoc.md">INVOC</a> structure containing the printer command to select the code page's symbol set.


### -field UnSelectSymbolSet

Is an <a href="..\prntfont\ns-prntfont-_invoc.md">INVOC</a> structure containing the printer command to deselect the code page's symbol set.


## -see-also

<a href="..\prntfont\ns-prntfont-_invoc.md">INVOC</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20UNI_CODEPAGEINFO structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


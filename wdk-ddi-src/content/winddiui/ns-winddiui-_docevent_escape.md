---
UID: NS:winddiui._DOCEVENT_ESCAPE
title: "_DOCEVENT_ESCAPE"
author: windows-driver-content
description: The DOCEVENT_ESCAPE structure is a container for values used as parameters for the ExtEscape function.
old-location: print\docevent_escape.htm
old-project: print
ms.assetid: 54ac7c45-63a1-4003-8250-524e6f9e8d06
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: winddiui/PDOCEVENT_ESCAPE, DOCEVENT_ESCAPE structure [Print Devices], DOCEVENT_ESCAPE, PDOCEVENT_ESCAPE, print_interface-graphics_943033df-71a2-4689-a9fb-abd9feb4ea0d.xml, print.docevent_escape, _DOCEVENT_ESCAPE, winddiui/DOCEVENT_ESCAPE, PDOCEVENT_ESCAPE structure pointer [Print Devices], *PDOCEVENT_ESCAPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winddiui.h
req.include-header: Winddiui.h
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
-	winddiui.h
apiname:
-	DOCEVENT_ESCAPE
product: Windows
targetos: Windows
req.typenames: "*PDOCEVENT_ESCAPE, DOCEVENT_ESCAPE"
req.product: Windows 10 or later.
---

# _DOCEVENT_ESCAPE structure


## -description


The DOCEVENT_ESCAPE structure is a container for values used as parameters for the <b>ExtEscape</b> function.


## -syntax


````
typedef struct _DOCEVENT_ESCAPE {
  int   iEscape;
  int   cjInput;
  PVOID pvInData;
} DOCEVENT_ESCAPE, *PDOCEVENT_ESCAPE;
````


## -struct-fields




### -field iEscape

Specifies the value of the <b>ExtEscape</b> function's <i>nEscape</i> parameter.


### -field cjInput

Specifies the value of the <b>ExtEscape</b> function's <i>cbInput</i> parameter.


### -field pvInData

Specifies the value of the <b>ExtEscape</b> function's <i>lpszInData</i> parameter.


## -remarks



The DOCEVENT_ESCAPE structure is defined for Windows XP and later.

This structure is used in conjunction with a call to <a href="..\winddiui\nf-winddiui-drvdocumentevent.md">DrvDocumentEvent</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff554141">IPrintOemUI2::DocumentEvent</a>, in which the <i>iEsc</i> parameter is set to DOCUMENTEVENT_ESCAPE. Before calling either of these functions, the caller must fill in the members of this structure.

Refer to the Microsoft Windows SDK documentation for a description of the <b>ExtEscape</b> function and the three parameters that correspond to the members of this structure. 




## -see-also

<a href="..\winddiui\nf-winddiui-drvdocumentevent.md">DrvDocumentEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554141">IPrintOemUI2::DocumentEvent</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20DOCEVENT_ESCAPE structure%20 RELEASE:%20(2/21/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


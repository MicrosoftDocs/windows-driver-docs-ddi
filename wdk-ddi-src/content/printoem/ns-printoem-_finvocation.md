---
UID: NS:printoem._FINVOCATION
title: "_FINVOCATION"
author: windows-driver-content
description: The FINVOCATION structure is used as input to the IPrintOemUni::SendFontCmd method. The structure is defined in printoem.h.
old-location: print\finvocation.htm
old-project: print
ms.assetid: 958d6f1f-e8e8-43e6-a4d4-73bae4b2be21
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PFINVOCATION, FINVOCATION, FINVOCATION structure [Print Devices], PFINVOCATION, PFINVOCATION structure pointer [Print Devices], _FINVOCATION, print.finvocation, print_unidrv-pscript_rendering_9937cdea-eacb-457c-af51-d8963ffd59e9.xml, printoem/FINVOCATION, printoem/PFINVOCATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	printoem.h
apiname:
-	FINVOCATION
product: Windows
targetos: Windows
req.typenames: FINVOCATION, *PFINVOCATION
req.product: Windows 10 or later.
---

# _FINVOCATION structure


## -description


The FINVOCATION structure is used as input to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554274">IPrintOemUni::SendFontCmd</a> method. The structure is defined in printoem.h.


## -syntax


````
typedef struct _FINVOCATION {
  DWORD dwCount;
  PBYTE pubCommand;
} FINVOCATION, *PFINVOCATION;
````


## -struct-fields




### -field dwCount

Specifies the Unidrv-supplied length, in bytes, of the command pointed to by <b>pubCommand</b>.


### -field pubCommand

Unidrv-supplied pointer to a string containing the printer's font selection command. The command is obtained from the font's .ufm (Unidrv Font Metrics) file.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554274">IPrintOemUni::SendFontCmd</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20FINVOCATION structure%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


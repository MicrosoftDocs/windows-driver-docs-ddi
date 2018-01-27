---
UID: NS:compstui._SETRESULT_INFO
title: _SETRESULT_INFO
author: windows-driver-content
description: The SETRESULT_INFO structure is used as an input parameter to an application's PFNPROPSHEETUI-typed callback function.
old-location: print\setresult_info.htm
old-project: print
ms.assetid: 54701f88-1145-4a50-bf5a-36be1d88355d
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: *PSETRESULT_INFO, PSETRESULT_INFO, compstui/PSETRESULT_INFO, SETRESULT_INFO structure [Print Devices], _SETRESULT_INFO, compstui/SETRESULT_INFO, cpsuifnc_df5b07fc-1a38-4ae2-a994-2862d9791b10.xml, SETRESULT_INFO, PSETRESULT_INFO structure pointer [Print Devices], print.setresult_info
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: compstui.h
req.include-header: Compstui.h
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
-	compstui.h
apiname: 
-	SETRESULT_INFO
product: Windows
targetos: Windows
req.typenames: *PSETRESULT_INFO, SETRESULT_INFO
---

# _SETRESULT_INFO structure


## -description


The SETRESULT_INFO structure is used as an input parameter to an application's <a href="..\compstui\nc-compstui-pfnpropsheetui.md">PFNPROPSHEETUI</a>-typed callback function. 


## -syntax


````
typedef struct _SETRESULT_INFO {
  WORD    cbSize;
  WORD    wReserved;
  HANDLE  hSetResult;
  LRESULT Result;
} SETRESULT_INFO, *PSETRESULT_INFO;
````


## -struct-fields




### -field cbSize

CPSUI-supplied size, in bytes, of the SETRESULT_INFO structure.


### -field wReserved

Reserved.


### -field hSetResult

CPSUI-supplied handle to an added property sheet page, obtained from the application. For more information, see the following Remarks section.


### -field Result

CPSUI-supplied handle to an added property sheet page, obtained from the application. For more information, see the following Remarks section.


## -remarks


When an application calls CPSUI's <a href="https://msdn.microsoft.com/library/windows/hardware/ff546207">ComPropSheet</a> function, specifying a function code of <a href="https://msdn.microsoft.com/library/windows/hardware/ff547087">CPSFUNC_SET_RESULT</a>, CPSUI calls all registered <a href="..\compstui\nc-compstui-pfnpropsheetui.md">PFNPROPSHEETUI</a>-typed functions, specifying a reason of PROPSHEETUI_REASON_SET_RESULT. When specifying this reason, CPSUI also supplies a SETRESULT_INFO structure.

The values contained in the structure's <b>hSetResult</b> and <b>Result</b> members are the <i>lParam1</i> and <i>lParam2</i> values, respectively, that were supplied to CPSUI's <b>ComPropSheet</b> function.

Each of the application's PFNPROPSHEETUI-typed functions is called in order, from the one most recently declared to the first one declared, until one of these functions provides a return value of less than one. At that point, CPSUI returns from its <b>ComPropSheet</b> function, providing a count of the number of PFNPROPSHEETUI-typed functions that were called.

Typically, an application's PFNPROPSHEETUI-typed function sets the <b>Result</b> member of its PROPSHEETUI_INFO structure to the value received in the SETRESULT_INFO structure's <b>Result</b> member. Then the function returns a value of 1 (or greater), so the next PFNPROPSHEETUI-typed function can also receive it. Each subsequently called function is associated with a page that is the parent of the page associated with the last-called function. A function can modify the contents of SETRESULT_INFO structure's <b>Result</b> member, causing the functions associated with parent pages to receive the new value.



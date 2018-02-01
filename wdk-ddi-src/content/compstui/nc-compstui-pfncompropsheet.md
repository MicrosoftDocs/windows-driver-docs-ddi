---
UID: NC:compstui.PFNCOMPROPSHEET
title: PFNCOMPROPSHEET
author: windows-driver-content
description: The ComPropSheet function is supplied by CPSUI and can be called by CPSUI applications (including printer interface DLLs) to build property sheet pages.
old-location: print\compropsheet.htm
old-project: print
ms.assetid: d9654346-1f28-4e02-8f6c-17e37ed09b92
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: print.compropsheet, ComPropSheet routine [Print Devices], ComPropSheet, PFNCOMPROPSHEET, PFNCOMPROPSHEET, compstui/ComPropSheet, cpsuifnc_2586427b-a3ae-4c2e-b081-06d58ec310c3.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: compstui.h
req.include-header: Compstui.h
req.target-type: Desktop
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
-	UserDefined
apilocation:
-	compstui.h
apiname:
-	ComPropSheet
product: Windows
targetos: Windows
req.typenames: "*PPOWERSOURCEUPDATEEX, POWERSOURCEUPDATEEX"
---

# PFNCOMPROPSHEET callback


## -description


The <i>ComPropSheet</i> function is supplied by <a href="https://msdn.microsoft.com/7af3435a-19e0-40a1-9f94-319d9d323856">CPSUI</a> and can be called by CPSUI applications (including printer interface DLLs) to build property sheet pages.


## -prototype


````
PFNCOMPROPSHEET ComPropSheet;

LONG_PTR CALLBACK ComPropSheet(
  _In_ HANDLE hComPropSheet,
  _In_ UINT   Function,
  _In_ LPARAM lParam1,
  _In_ LPARAM lParam2
)
{ ... }
````


## -parameters




### -param hComPropSheet [in]

Caller-supplied handle to a property sheet <a href="https://msdn.microsoft.com/b4c40c15-df16-4af0-81c8-9e70d26ba598">group parent</a>. For more information, see the following Remarks section.


### -param Function [in]

Caller-supplied, CPSFUNC_-prefixed <a href="https://msdn.microsoft.com/library/windows/hardware/ff546214">ComPropSheet function codes</a> specifying the operation to be performed by the <i>ComPropSheet</i> function.


### -param lParam1 [in]

Caller-supplied value that depends on the <i>ComPropSheet</i> function code supplied for <i>Function</i>.


### -param lParam2 [in]

Caller-supplied value that depends on the <i>ComPropSheet</i> function code supplied for <i>Function</i>.


## -returns


The return value depends on the <a href="https://msdn.microsoft.com/ae0755a2-49fc-4297-91dd-46beaa5349a5">ComPropSheet function code</a> supplied for <i>Function</i>.



## -remarks


When CPSUI calls one of an application's <a href="..\compstui\nc-compstui-pfnpropsheetui.md">PFNPROPSHEETUI</a>-typed functions, it passes a pointer to the <i>ComPropSheet</i> function in a <a href="..\compstui\ns-compstui-_propsheetui_info.md">PROPSHEETUI_INFO</a> structure. A <b>PFNPROPSHEETUI</b>-typed function can call the <i>ComPropSheet</i> function to describe property sheet pages to CPSUI.

A <a href="https://msdn.microsoft.com/2a8cf38f-8e27-4e08-9c0f-5d1a4cd854ac">printer interface DLL</a> can call <i>ComPropSheet</i> from within its <a href="..\winddiui\nf-winddiui-drvdocumentpropertysheets.md">DrvDocumentPropertySheets</a> function or its <a href="..\winddiui\nf-winddiui-drvdevicepropertysheets.md">DrvDevicePropertySheets</a> function.


<a href="https://msdn.microsoft.com/22ac2af6-37d8-4913-95af-9c3dc8576d40">User interface plug-ins</a> for Microsoft's <a href="https://msdn.microsoft.com/0a51fa2b-3d09-4a5f-9fff-40604877a414">Unidrv</a> and <a href="https://msdn.microsoft.com/139a10e9-203b-499b-9291-8537eae9189c">Pscript</a> drivers can call <i>ComPropSheet</i> from within their <a href="https://msdn.microsoft.com/library/windows/hardware/ff554173">IPrintOemUI::DocumentPropertySheets</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff554165">IPrintOemUI::DevicePropertySheets</a> methods.

The <a href="https://msdn.microsoft.com/b4c40c15-df16-4af0-81c8-9e70d26ba598">group parent</a> handle specified for the <i>hComPropSheet</i> parameter can be either of the following:
<ul>
<li>
The handle received in the <i>hComPropSheet</i> member of a <a href="..\compstui\ns-compstui-_propsheetui_info.md">PROPSHEETUI_INFO</a> structure.

</li>
<li>
The handle received as a result of previously calling <i>ComPropSheet</i> with a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546414">CPSFUNC_INSERT_PSUIPAGE</a> function code, and specifying PSUIPAGEINSERT_GROUP_PARENT as the <b>Type</b> member for an <a href="..\compstui\ns-compstui-_insertpsuipage_info.md">INSERTPSUIPAGE_INFO</a> structure.

</li>
</ul>


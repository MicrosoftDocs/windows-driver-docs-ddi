---
UID: NF:wdbgexts.GetSetSympath
title: GetSetSympath function
author: windows-driver-content
description: The GetSetSympath function can be used to either get or set the symbol search path.
old-location: debugger\getsetsympath.htm
tech.root: debugger
ms.assetid: 2c7392c2-49c8-4b27-addc-0200eabbe87e
ms.date: 5/3/2018
ms.keywords: GetSetSympath, GetSetSympath function [Windows Debugging], WdbgExts_Ref_66364d7b-fd3c-424a-a04d-b7bf24178039.xml, debugger.getsetsympath, wdbgexts/GetSetSympath
ms.topic: function
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdbgexts.h
api_name:
-	GetSetSympath
product:
- Windows
targetos: Windows
req.typenames: 
---

# GetSetSympath function


## -description


The <b>GetSetSympath</b> function can be used to either get or set the symbol search path. 


## -parameters




### -param Arg [in]

Specifies the new search path. If this argument is <b>NULL</b> or the string is empty, the search path is not set and the current setting is returned in <i>Result</i>.


### -param OPTIONAL

<p>Optional. If <i>Arg</i> is <b>NULL</b>, <b>GetSetSympath</b> stores the current search path in the buffer pointed to by <i>Result</i>.</p>


### -param Length [in]

Specifies the size of the buffer for storing the result.


## -returns



None

<h2><a id="ddk_getsetsympath_dbwx"></a><a id="DDK_GETSETSYMPATH_DBWX"></a></h2>



## -remarks



When the symbol path is changed, a call to <b>ReloadSymbols</b> is made implicitly.




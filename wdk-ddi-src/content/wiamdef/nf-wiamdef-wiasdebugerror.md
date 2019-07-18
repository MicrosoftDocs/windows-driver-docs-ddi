---
UID: NF:wiamdef.wiasDebugError
title: wiasDebugError function (wiamdef.h)
description: This function prints a debug error string in the Device Manager debug console. The output color is always red.
old-location: image\wiasdebugerror.htm
tech.root: image
ms.assetid: fcddc83d-5fb1-43ad-9abd-8d5e2549b580
ms.date: 05/03/2018
ms.keywords: image.wiasdebugerror, wiamdef/wiasDebugError, wiasDebugError, wiasDebugError function [Imaging Devices], wiasFncs_0ccba388-a6ca-42b9-acd5-720b6763a202.xml
ms.topic: function
f1_keywords:
 - "wiamdef/wiasDebugError"
req.header: wiamdef.h
req.include-header: Wiamdef.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows Me and in Windows XP and later versions of the Windows operating systems.
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
req.lib: Wiaservc.lib
req.dll: Wiaservc.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Wiaservc.dll
api_name:
- wiasDebugError
product:
- Windows
targetos: Windows
req.typenames: 
---

# wiasDebugError function


## -description


This function prints a debug error string in the Device Manager debug console. The output color is always red.


## -parameters




### -param hInstance

Is the module handle of calling module.


### -param pszFormat




### -param param






####### - pszFormat, ...

Specifies a variable argument list, which starts with an ANSI format string containing the message and any format specifiers. The ellipsis (...) specifies a variable number of arguments that are to be output.


## -returns



On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).




## -remarks



The wiasDebugError function is not recommended for Windows XP and later. For Windows XP use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wias_lerror">WIAS_LERROR</a> macro instead. For Windows Vista use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wias_error">WIAS_ERROR</a> macro instead.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wias_error">WIAS_ERROR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wias_lerror">WIAS_LERROR</a>
 

 


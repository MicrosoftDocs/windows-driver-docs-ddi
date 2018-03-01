---
UID: NS:dbgeng._DEBUG_EXCEPTION_FILTER_PARAMETERS
title: "_DEBUG_EXCEPTION_FILTER_PARAMETERS"
author: windows-driver-content
description: The DEBUG_EXCEPTION_FILTER_PARAMETERS structure contains the parameters for an exception filter.
old-location: debugger\debug_exception_filter_parameters.htm
old-project: debugger
ms.assetid: 26a101c5-0866-44e3-948b-8d3ca4dd9d00
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PDEBUG_EXCEPTION_FILTER_PARAMETERS, DEBUG_EXCEPTION_FILTER_PARAMETERS, DEBUG_EXCEPTION_FILTER_PARAMETERS structure [Windows Debugging], PDEBUG_EXCEPTION_FILTER_PARAMETERS, PDEBUG_EXCEPTION_FILTER_PARAMETERS structure pointer [Windows Debugging], Structures_f3f2b1ac-e10c-439e-9de9-6b4161bf3c28.xml, _DEBUG_EXCEPTION_FILTER_PARAMETERS, dbgeng/DEBUG_EXCEPTION_FILTER_PARAMETERS, dbgeng/PDEBUG_EXCEPTION_FILTER_PARAMETERS, debugger.debug_exception_filter_parameters"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dbgeng.h
req.include-header: DbgEng.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	DbgEng.h
api_name:
-	DEBUG_EXCEPTION_FILTER_PARAMETERS
product: Windows
targetos: Windows
req.typenames: DEBUG_EXCEPTION_FILTER_PARAMETERS, *PDEBUG_EXCEPTION_FILTER_PARAMETERS
---

# _DEBUG_EXCEPTION_FILTER_PARAMETERS structure


## -description


The DEBUG_EXCEPTION_FILTER_PARAMETERS structure contains the parameters for an exception filter.


## -syntax


````
typedef struct _DEBUG_EXCEPTION_FILTER_PARAMETERS {
  ULONG ExecutionOption;
  ULONG ContinueOption;
  ULONG TextSize;
  ULONG CommandSize;
  ULONG SecondCommandSize;
  ULONG ExceptionCode;
} DEBUG_EXCEPTION_FILTER_PARAMETERS, *PDEBUG_EXCEPTION_FILTER_PARAMETERS;
````


## -struct-fields




### -field ExecutionOption

The <a href="https://msdn.microsoft.com/1f8f738b-7b2b-419a-949e-b71f937de02d">break status</a> of the exception filter, including the terminator.  For possible values, see <b>DEBUG_FILTER_XXX</b>.


### -field ContinueOption

The <a href="https://msdn.microsoft.com/1f8f738b-7b2b-419a-949e-b71f937de02d">handling status</a> of the exception filter.  For possible values, see <b>DEBUG_FILTER_XXX</b>.


### -field TextSize

The size, in characters, of the name (including the terminator) of the exception filter.  If the filter is an arbitrary exception filter, it does not have a name and <b>TextSize</b> is zero.


### -field CommandSize

The size, in characters, of the command (including the terminator) to execute upon the first chance of the exception.


### -field SecondCommandSize

The size, in characters, of the command (including the terminator) to execute upon the second chance of the exception.


### -field ExceptionCode

The exception code for the exception filter.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546650">GetExceptionFilterParameters</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556683">SetExceptionFilterParameters</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20DEBUG_EXCEPTION_FILTER_PARAMETERS structure%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


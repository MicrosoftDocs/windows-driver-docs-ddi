---
UID: NF:engextcpp.EXT_COMMAND
title: EXT_COMMAND macro (engextcpp.h)
description: The EXT_COMMAND macro is used to define an extension command that was declared by using the EXT_COMMAND_METHOD macro.An extension command is defined as follows.
old-location: debugger\ext_command.htm
tech.root: debugger
ms.assetid: 349712b1-bd1f-4f1f-a242-b6aa36e48773
ms.date: 05/03/2018
keywords: ["EXT_COMMAND macro"]
ms.keywords: EXT_COMMAND, EXT_COMMAND function [Windows Debugging], EngExtCpp_Ref_a6dc21d7-b0c2-4e13-add5-ecfe3c38a94a.xml, debugger.ext_command, engextcpp/EXT_COMMAND
req.header: engextcpp.hpp
req.include-header: Engextcpp.hpp
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
targetos: Windows
req.typenames: 
f1_keywords:
 - EXT_COMMAND
 - engextcpp/EXT_COMMAND
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - engextcpp.hpp
api_name:
 - EXT_COMMAND
---

# EXT_COMMAND macro


## -description

The EXT_COMMAND macro is used to define an extension command that was declared by using the <a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-ext_command_method">EXT_COMMAND_METHOD</a> macro.

An extension command is defined as follows:

## -parameters

### -param _Name

The name of the extension command.  This must be the same as the <i>_Name</i> parameter that is used to declare the extension command by using <a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-ext_command_method">EXT_COMMAND_METHOD</a>.

Because EXT_COMMAND is a macro, <i>_Name</i> must be the bare name of the extension command and should not be enclosed in quotation marks or be a variable.

### -param _Desc

A string describing the extension command.

### -param _Args

A string describing the arguments that are expected by the extension command.   For information about how the <i>_Args</i> string is formatted, see <a href="/windows-hardware/drivers/debugger/parsing-extension-arguments">Parsing Extension Arguments</a>.

<div class="alert"><b>Note</b>     As an alternative to supplying a string that describes the arguments, you can use  the string "{{custom}}" to indicate that the extension command will parse the arguments itself.  The method <a href="/previous-versions/windows/hardware/previsioning-framework/ff548226(v=vs.85)">GetRawArgStr</a> can be used to fetch the raw argument for parsing.</div>
<div> </div>

## -remarks

The body of the extension command does not take any arguments.  However, because the extension command is declared as a method of the <a href="/previous-versions/ff544508(v=vs.85)">EXT_CLASS</a> class, it has access to all the members of the <a href="/previous-versions/ff543981(v=vs.85)">ExtExtension</a> base class, some of which are initialized for the execution of the extension command.

The macro <a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-ext_command_method">EXT_COMMAND_METHOD</a> should be used to declare the extension command.  As with all C++ declarations, the EXT_COMMAND_METHOD declaration should appear in the source files before the EXT_COMMAND definition.

When the debugger engine calls an extension command method, it wraps the call in a <b>try / except</b> block.  This protects the engine from some types of bugs in the extension code; but, since the extension calls are executed in the same thread as the engine, they can still cause it to crash.

This macro also creates a function called <i>_Name</i> (which calls the method defined by the macro).  In order for the engine to call the extension, this function must be exported from the extension library DLL.

The <a href="/previous-versions/ff544508(v=vs.85)">EXT_CLASS</a> constant specifies the name of the C++ class that represents the EngExtCpp extension library.

EXT_CLASS


```cpp
    #ifndef EXT_CLASS
    #define EXT_CLASS Extension
    #endif
```

The default value of <a href="/previous-versions/ff544508(v=vs.85)">EXT_CLASS</a> is <b>Extension</b>.  You can change this value  by defining EXT_CLASS before you include the header file Engextcpp.hpp.

Each extension command in the library is declared as a member of the class EXT_CLASS using the macro <a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-ext_command_method">EXT_COMMAND_METHOD</a>.  For example, a library with two extension commands, <b>extcmd</b> and <b>anotherextcmd</b>, could define the class EXT_CLASS as follows:


```
class EXT_CLASS : public ExtExtension
{
public:
    EXT_COMMAND_METHOD(extcmd);
    EXT_COMMAND_METHOD(anotherextcmd);
}
```

Extension commands that have been declared by using EXT_COMMAND_METHOD should be defined by using <b>EXT_COMMAND</b> and should be exported from the library.

The <a href="/previous-versions/ff544527(v=vs.85)">EXT_DECLARE_GLOBALS</a> macro creates a single instance of the EXT_CLASS class.

The <a href="/previous-versions/ff544527(v=vs.85)">EXT_DECLARE_GLOBALS</a> macro sets up some global variables for use by the EngExtCpp extension framework.  This include creating a single instance of the <a href="/previous-versions/ff544508(v=vs.85)">EXT_CLASS</a> class that represents the EngExtCpp extension library.

One of the source files to be compiled into the EngExtCpp extension library should include the following command


```
EXT_DECLARE_GLOBALS()
```


## -see-also

<a href="/previous-versions/ff544508(v=vs.85)">EXT_CLASS</a>



<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-ext_command_method">EXT_COMMAND_METHOD</a>



<a href="/previous-versions/ff543981(v=vs.85)">ExtExtension</a>
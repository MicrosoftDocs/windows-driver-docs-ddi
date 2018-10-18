---
UID: NL:engextcpp.ExtExtension~r1
title: ExtExtension
author: windows-driver-content
description: The ExtExtension class is the base class for the C++ class that represents the EngExtCpp extension library.
old-location: debugger\extextension.htm
tech.root: debugger
ms.assetid: 9c6c4633-df49-4f49-8116-d680bb20c3f5
ms.date: 2/22/2018
ms.keywords: EngExtCpp_Ref_3a533353-f008-4887-b937-2098acf1c68e.xml, ExtExtension, ExtExtension class [Windows Debugging], ExtExtension class [Windows Debugging], described, debugger.extextension, engextcpp/ExtExtension
ms.topic: class
req.header: engextcpp.hpp
req.include-header:
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
req.lib: engextcpp.hpp
req.dll:
req.irql:
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	engextcpp.hpp
apiname:
-	ExtExtension
product:
- Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtExtension class


## -description


The <b>ExtExtension</b> class is the base class for the C++ class that represents the EngExtCpp extension library.

The <b>ExtExtension</b> class includes the following methods, which can be used by the subclass:
<dl>
<dd>

<a href="..\engextcpp\nf-engextcpp-extextension-initialize.md">Initialize</a>


</dd>
<dd>

<a href="..\engextcpp\nf-engextcpp-extextension-uninitialize.md">Uninitialize</a>


</dd>
<dd>

<a href="..\engextcpp\nf-engextcpp-extextension-onsessionactive.md">OnSessionActive</a>


</dd>
<dd>

<a href="..\engextcpp\nf-engextcpp-extextension-onsessioninactive.md">OnSessionInactive</a>


</dd>
<dd>

<a href="..\engextcpp\nf-engextcpp-extextension-onsessionaccessible.md">OnSessionAccessible</a>


</dd>
<dd>

<a href="..\engextcpp\nf-engextcpp-extextension-onsessioninaccessible.md">OnSessionInaccessible</a>


</dd>
<dd>
<b>IsUserMode</b>

</dd>
<dd>
<b>IsKernelMode</b>

</dd>
<dd>
<b>IsLiveLocalUser</b>

</dd>
<dd>
<b>IsMachine32</b>

</dd>
<dd>
<b>IsCurMachine32</b>

</dd>
<dd>
<b>IsMachine64</b>

</dd>
<dd>
<b>IsCurMachine64</b>

</dd>
<dd>
<b>Is32On64</b>

</dd>
<dd>
<b>CanQueryVirtual</b>

</dd>
<dd>
<b>HasFullMemBasic</b>

</dd>
<dd>
<b>IsExtensionRemote</b>

</dd>
<dd>
<b>AreOutputCallbacksDmlAware</b>

</dd>
<dd>
<b>RequireUserMode</b>

</dd>
<dd>
<b>RequireKernelMode</b>

</dd>
<dd>

<a href="..\engextcpp\nf-engextcpp-extextension-getnumunnamedargs.md">GetNumUnnamedArgs</a>


</dd>
<dd>

<a href="..\engextcpp\nf-engextcpp-extextension-getunnamedargstr.md">GetUnnamedArgStr</a>


</dd>
<dd>

<a href="..\engextcpp\nf-engextcpp-extextension-getunnamedargu64.md">GetUnnamedArgU64</a>


</dd>
<dd>

<a href="..\engextcpp\nf-engextcpp-extextension-hasunnamedarg.md">HasUnnamedArg</a>


</dd>
<dd>

<a href="..\engextcpp\nf-engextcpp-extextension-getargstr.md">GetArgStr</a>


</dd>
<dd>

<a href="..\engextcpp\nf-engextcpp-extextension-getargu64.md">GetArgU64</a>


</dd>
<dd>

<a href="..\engextcpp\nf-engextcpp-extextension-hasarg.md">HasArg</a>


</dd>
<dd>

<a href="..\engextcpp\nf-engextcpp-extextension-haschararg.md">HasCharArg</a>


</dd>
<dd>

<a href="..\engextcpp\nf-engextcpp-extextension-setunnamedarg.md">SetUnnamedArg</a>


</dd>
<dd>

<a href="..\engextcpp\nf-engextcpp-extextension-setunnamedargstr.md">SetUnnamedArgStr</a>


</dd>
<dd>

<a href="..\engextcpp\nf-engextcpp-extextension-setunnamedargu64.md">SetUnnamedArgU64</a>


</dd>
<dd>

<a href="..\engextcpp\nf-engextcpp-extextension-setarg.md">SetArg</a>


</dd>
<dd>

<a href="..\engextcpp\nf-engextcpp-extextension-setargstr.md">SetArgStr</a>


</dd>
<dd>

<a href="..\engextcpp\nf-engextcpp-extextension-setargu64.md">SetArgU64</a>


</dd>
<dd>

<a href="..\engextcpp\nf-engextcpp-extextension-getrawargstr.md">GetRawArgStr</a>


</dd>
<dd>
<b>GetRawArgCopy</b>

</dd>
<dd>
<b>Out</b>

</dd>
<dd>
<b>Warn</b>

</dd>
<dd>
<b>Err</b>

</dd>
<dd>
<b>Verb</b>

</dd>
<dd>
<b>Dml</b>

</dd>
<dd>
<b>DmlWarn</b>

</dd>
<dd>
<b>DmlErr</b>

</dd>
<dd>
<b>DmlVerb</b>

</dd>
<dd>
<b>DmlCmdLink</b>

</dd>
<dd>
<b>DmlCmdExec</b>

</dd>
<dd>
<b>RefreshOutputCallbackFlags</b>

</dd>
<dd>
<b>WrapLine</b>

</dd>
<dd>
<b>OutWrapStr</b>

</dd>
<dd>
<b>OutWrapVa</b>

</dd>
<dd>
<b>OutWrap</b>

</dd>
<dd>
<b>DemandWrap</b>

</dd>
<dd>
<b>AllowWrap</b>

</dd>
<dd>
<b>TestWrap</b>

</dd>
<dd>
<b>RequestCircleString</b>

</dd>
<dd>
<b>CopyCircleString</b>

</dd>
<dd>
<b>PrintCircleStringVa</b>

</dd>
<dd>
<b>PrintCircleString</b>

</dd>
<dd>
<b>SetAppendBuffer</b>

</dd>
<dd>
<b>AppendBufferString</b>

</dd>
<dd>
<b>AppendStringVa</b>

</dd>
<dd>
<b>AppendString</b>

</dd>
<dd>
<b>IsAppendStart</b>

</dd>
<dd>
<b>SetCallStatus</b>

</dd>
<dd>
<b>GetCachedSymbolTypeId</b>

</dd>
<dd>
<b>GetCachedFieldOffset</b>

</dd>
<dd>
<b>GetCachedFieldOffset</b>

</dd>
<dd>
<b>AddCachedSymbolInfo</b>

</dd>
<dd>
<b>GetExpr64</b>

</dd>
<dd>
<b>GetExprU64</b>

</dd>
<dd>
<b>GetExprS64</b>

</dd>
<dd>
<b>ThrowCommandHelp</b>

</dd>
<dd>
<b>ThrowInterrupt</b>

</dd>
<dd>
<b>ThrowOutOfMemory</b>

</dd>
<dd>
<b>ThrowContinueSearch</b>

</dd>
<dd>
<b>ThrowReloadExtension</b>

</dd>
<dd>
<b>ThrowInvalidArg</b>

</dd>
<dd>
<b>ThrowRemote</b>

</dd>
<dd>
<b>ThrowStatus</b>

</dd>
<dd>
<b>ThrowLastError</b>

</dd>
</dl>The <b>ExtExtension</b> class also contains the following fields that can be used by the subclass:
<pre class="syntax" xml:space="preserve"><code>class ExtExtension
{
public:
    USHORT  m_ExtMajorVersion;
    USHORT  m_ExtMinorVersion;
    ULONG  m_ExtInitFlags;
    ExtKnownStruct *  m_KnownStructs;
    ExtProvidedValue *  m_ProvidedValues;
    ExtCheckedPointer&lt;IDebugAdvanced&gt;  m_Advanced;
    ExtCheckedPointer&lt;IDebugClient&gt;  m_Client;
    ExtCheckedPointer&lt;IDebugControl&gt;  m_Control;
    ExtCheckedPointer&lt;IDebugDataSpaces&gt;  m_Data;
    ExtCheckedPointer&lt;IDebugRegisters&gt;  m_Registers;
    ExtCheckedPointer&lt;IDebugSymbols&gt;  m_Symbols;
    ExtCheckedPointer&lt;IDebugSystemObjects&gt;  m_System;
    ExtCheckedPointer&lt;IDebugAdvanced2&gt;  m_Advanced2;
    ExtCheckedPointer&lt;IDebugAdvanced3&gt;  m_Advanced3;
    ExtCheckedPointer&lt;IDebugClient2&gt;  m_Client2;
    ExtCheckedPointer&lt;IDebugClient3&gt;  m_Client3;
    ExtCheckedPointer&lt;IDebugClient4&gt;  m_Client4;
    ExtCheckedPointer&lt;IDebugClient5&gt;  m_Client5;
    ExtCheckedPointer&lt;IDebugControl2&gt;  m_Control2;
    ExtCheckedPointer&lt;IDebugControl3&gt;  m_Control3;
    ExtCheckedPointer&lt;IDebugControl4&gt;  m_Control4;
    ExtCheckedPointer&lt;IDebugDataSpaces2&gt;  m_Data2;
    ExtCheckedPointer&lt;IDebugDataSpaces3&gt;  m_Data3;
    ExtCheckedPointer&lt;IDebugDataSpaces4&gt;  m_Data4;
    ExtCheckedPointer&lt;IDebugRegisters2&gt;  m_Registers2;
    ExtCheckedPointer&lt;IDebugSymbols2&gt;  m_Symbols2;
    ExtCheckedPointer&lt;IDebugSymbols3&gt;  m_Symbols3;
    ExtCheckedPointer&lt;IDebugSystemObjects2&gt;  m_System2;
    ExtCheckedPointer&lt;IDebugSystemObjects3&gt;  m_System3;
    ExtCheckedPointer&lt;IDebugSystemObjects4&gt;  m_System4;
    ULONG  m_OutputWidth;
    ULONG  m_ActualMachine;
    ULONG  m_Machine;
    ULONG  m_PageSize;
    ULONG  m_PtrSize;
    ULONG  m_NumProcessors;
    ULONG64  m_OffsetMask;
    ULONG  m_DebuggeeClass;
    ULONG  m_DebuggeeQual;
    ULONG  m_DumpFormatFlags;
    bool  m_IsRemote;
    bool  m_OutCallbacksDmlAware;
    ULONG  m_OutMask;
    ULONG  m_CurChar;
    ULONG  m_LeftIndent;
    bool  m_AllowWrap;
    bool  m_TestWrap;
    ULONG  m_TestWrapChars;
    PSTR  m_AppendBuffer;
    ULONG  m_AppendBufferChars;
    PSTR  m_AppendAt;
};


</code></pre>

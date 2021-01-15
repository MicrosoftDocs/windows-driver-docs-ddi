---
UID: NF:dbgeng.IDebugControl3.GetWindbgExtensionApis64
title: IDebugControl3::GetWindbgExtensionApis64 (dbgeng.h)
description: The GetWindbgExtensionApis64 method returns a structure that facilitates using the WdbgExts API.
old-location: debugger\getwindbgextensionapis64.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugControl3::GetWindbgExtensionApis64"]
ms.keywords: GetWindbgExtensionApis64, GetWindbgExtensionApis64 method [Windows Debugging], GetWindbgExtensionApis64 method [Windows Debugging],IDebugControl interface, GetWindbgExtensionApis64 method [Windows Debugging],IDebugControl2 interface, GetWindbgExtensionApis64 method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetWindbgExtensionApis64 method, IDebugControl2 interface [Windows Debugging],GetWindbgExtensionApis64 method, IDebugControl2::GetWindbgExtensionApis64, IDebugControl3 interface [Windows Debugging],GetWindbgExtensionApis64 method, IDebugControl3.GetWindbgExtensionApis64, IDebugControl3::GetWindbgExtensionApis64, IDebugControl::GetWindbgExtensionApis64, IDebugControl_51215e32-dcd3-440f-92ee-6ff82ae1c8e6.xml, dbgeng/IDebugControl2::GetWindbgExtensionApis64, dbgeng/IDebugControl3::GetWindbgExtensionApis64, dbgeng/IDebugControl::GetWindbgExtensionApis64, debugger.getwindbgextensionapis64
req.header: dbgeng.h
req.include-header: Wdbgexts.h, Dbgeng.h, Wdbgexts.h
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
 - IDebugControl3::GetWindbgExtensionApis64
 - dbgeng/IDebugControl3::GetWindbgExtensionApis64
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl3::GetWindbgExtensionApis64
---

# IDebugControl3::GetWindbgExtensionApis64


## -description

The <b>GetWindbgExtensionApis64</b> method returns a structure that facilitates using the WdbgExts API.

## -parameters

### -param Api 

[in, out]
Receives a WINDBG_EXTENSION_APIS64 structure.  This structure contains the functions used by the WdbgExts API.  The <b>nSize</b> member of this structure must be set to the size of the structure before it is passed to this method.

## -returns

This method may also return other error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
The value of <i>Api</i>-><b>nSize</b> does not equal the size of the structure WINDBG_EXTENSION_APIS64.

</td>
</tr>
</table>

## -remarks

If you are including Wdbgexts.h in your extension code, you should call this method during the initialization of the extension DLL (see <a href="/windows-hardware/drivers/ddi/dbgeng/nc-dbgeng-pdebug_extension_initialize">DebugExtensionInitialize</a>).

Many WdbgExts functions are really macros.  To ensure that these macros work correctly, the structure received by the <i>Api</i> parameter should be stored in a global variable named <b>ExtensionApis</b>.  

The WINDBG_EXTENSION_APIS64 structure returned by this method serves the same purpose as the one provided to the callback function <a href="/windows-hardware/drivers/ddi/wdbgexts/nc-wdbgexts-pwindbg_extension_dll_init">WinDbgExtensionDllInit</a> (used by WdbgExts extensions).

For a list of the functions provided by the WdbgExts API, see <a href="/windows-hardware/drivers/debugger/wdbgexts-functions">WdbgExts Functions</a>.


---
UID: NF:dbgeng.IDebugControl.GetWindbgExtensionApis32
title: IDebugControl::GetWindbgExtensionApis32 (dbgeng.h)
description: The GetWindbgExtensionApis32 method returns a structure that facilitates using the WdbgExts API.
old-location: debugger\idebugcontrol_getwindbgextensionapis32.htm
tech.root: debugger
ms.assetid: 84661E3C-9AC7-4852-BABF-BFC0A793E83D
ms.date: 05/03/2018
ms.keywords: GetWindbgExtensionApis32, GetWindbgExtensionApis32 method [Windows Debugging], GetWindbgExtensionApis32 method [Windows Debugging],IDebugControl interface, GetWindbgExtensionApis32 method [Windows Debugging],IDebugControl2 interface, GetWindbgExtensionApis32 method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetWindbgExtensionApis32 method, IDebugControl.GetWindbgExtensionApis32, IDebugControl2 interface [Windows Debugging],GetWindbgExtensionApis32 method, IDebugControl2::GetWindbgExtensionApis32, IDebugControl3 interface [Windows Debugging],GetWindbgExtensionApis32 method, IDebugControl3::GetWindbgExtensionApis32, IDebugControl::GetWindbgExtensionApis32, dbgeng/IDebugControl2::GetWindbgExtensionApis32, dbgeng/IDebugControl3::GetWindbgExtensionApis32, dbgeng/IDebugControl::GetWindbgExtensionApis32, debugger.idebugcontrol_getwindbgextensionapis32
ms.topic: method
f1_keywords:
 - "dbgeng/IDebugControl.GetWindbgExtensionApis32"
req.header: dbgeng.h
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dbgeng.h
api_name:
- IDebugControl.GetWindbgExtensionApis32
- IDebugControl2.GetWindbgExtensionApis32
- IDebugControl3.GetWindbgExtensionApis32
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl::GetWindbgExtensionApis32


## -description


The <b>GetWindbgExtensionApis32</b> method returns a structure that facilitates using the WdbgExts API.


## -parameters




### -param Api [in, out]

Receives a WINDBG_EXTENSION_APIS32 structure.  This structure contains the functions used by the WdbgExts API.  The <b>nSize</b> member of this structure must be set to the size of the structure before it is passed to this method.


## -returns



This method may also return other error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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
The value of <i>Api</i>-><b>nSize</b> does not equal the size of the structure WINDBG_EXTENSION_APIS32.

</td>
</tr>
</table>
 




## -remarks



If you are including Wdbgexts.h in your extension code, you should call this method during the initialization of the extension DLL (see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nc-dbgeng-pdebug_extension_initialize">DebugExtensionInitialize</a>).

Many WdbgExts functions are really macros.  To ensure that these macros work correctly, the structure received by the <i>Api</i> parameter should be stored in a global variable named <b>ExtensionApis</b>.  

For a list of the functions provided by the WdbgExts API, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/wdbgexts-functions">WdbgExts Functions</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nc-dbgeng-pdebug_extension_initialize">DebugExtensionInitialize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/wdbgexts-functions">WdbgExts Functions</a>
 

 


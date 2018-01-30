---
UID: NF:dbgeng.IDebugRegisters2.GetDescriptionWide
title: IDebugRegisters2::GetDescriptionWide method
author: windows-driver-content
description: The GetDescriptionWide method returns the description of a register.
old-location: debugger\getdescriptionwide.htm
old-project: debugger
ms.assetid: e599d960-aefb-4b68-8149-7e93150d90d5
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: GetDescriptionWide method [Windows Debugging], IDebugRegisters2 interface, dbgeng/IDebugRegisters2::GetDescriptionWide, IDebugRegisters2::GetDescriptionWide, debugger.getdescriptionwide, GetDescriptionWide method [Windows Debugging], IDebugRegisters2 interface [Windows Debugging], GetDescriptionWide method, IDebugRegisters2, GetDescriptionWide
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: DbgEng.h
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugRegisters2.GetDescriptionWide
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_GETENCRYPTIONBLTKEY
---

# IDebugRegisters2::GetDescriptionWide method


## -description


The <b>GetDescriptionWide</b>  method returns the description of a register.


## -syntax


````
HRESULT GetDescriptionWide(
  [in]            ULONG                       Register,
  [out, optional] PWSTR                       NameBuffer,
  [in]            ULONG                       NameBufferSize,
  [out, optional] PULONG                      NameSize,
  [out, optional] PDEBUG_REGISTER_DESCRIPTION Desc
);
````


## -parameters




### -param Register [in]

Specifies the index of the register for which the description is requested.


### -param NameBuffer [out, optional]

Specifies the buffer in which to store the name of the register.  If <i>NameBuffer</i> is <b>NULL</b>, this information is not returned.


### -param NameBufferSize [in]

Specifies the size, in characters, of the buffer that  <i>NameBuffer</i> specifies.


### -param NameSize [out, optional]

Receives the size, in characters, of the register's name in <i>NameBuffer</i> buffer.  If <i>NameSize</i> is <b>NULL</b>, this information is not returned.


### -param Desc [out, optional]

Receives the description of the register.  See <a href="..\dbgeng\ns-dbgeng-_debug_register_description.md">DEBUG_REGISTER_DESCRIPTION</a> for more details.


## -returns


This list does not contain all the errors that might occur.  For a list of possible errors, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff549771">HRESULT Values</a>.
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
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful. However, the buffer was not large enough to hold the register's name, so it was truncated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_UNEXPECTED</b></dt>
</dl>
</td>
<td width="60%">
No target machine has been specified, or a description of the register could not be found.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
The index of the register requested is greater than the total number of registers on the target's machine.

</td>
</tr>
</table> 



## -remarks


For an overview of the <a href="..\dbgeng\nn-dbgeng-idebugregisters.md">IDebugRegisters</a> interface and other register-related methods, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">Registers</a>.



---
UID: NF:dbgeng.IDebugRegisters2.GetPseudoDescriptionWide
title: IDebugRegisters2::GetPseudoDescriptionWide method
author: windows-driver-content
description: The GetPseudoDescriptionWide method returns a description of a pseudo-register, including its name and type.
old-location: debugger\getpseudodescriptionwide.htm
old-project: debugger
ms.assetid: fcf2409a-aedf-4de3-ad17-7edbc810f7be
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugRegisters2 interface [Windows Debugging], GetPseudoDescriptionWide method, IDebugRegisters2::GetPseudoDescriptionWide, GetPseudoDescriptionWide, dbgeng/IDebugRegisters2::GetPseudoDescriptionWide, GetPseudoDescriptionWide method [Windows Debugging], IDebugRegisters2, GetPseudoDescriptionWide method [Windows Debugging], IDebugRegisters2 interface, debugger.getpseudodescriptionwide
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
-	IDebugRegisters2.GetPseudoDescriptionWide
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugRegisters2::GetPseudoDescriptionWide method


## -description


The <b>GetPseudoDescriptionWide</b> method returns a description of a pseudo-register, including its name and type.


## -syntax


````
HRESULT GetPseudoDescriptionWide(
  [in]            ULONG    Register,
  [out, optional] PWSTR    NameBuffer,
  [in]            ULONG    NameBufferSize,
  [out, optional] PULONG   NameSize,
  [out, optional] PULONG64 TypeModule,
  [out, optional] PULONG   TypeId
);
````


## -parameters




### -param Register [in]

Specifies the index of the pseudo-register whose description is requested.  The index is always between zero and the number of pseudo-registers (returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff547957">GetNumberPseudoRegisters</a>) minus one.


### -param NameBuffer [out, optional]

Receives the name of the pseudo-register.  If <i>NameBuffer</i> is <b>NULL</b>, this information is not returned.


### -param NameBufferSize [in]

Specifies the size, in characters, of the buffer that <i>NameBuffer </i>specifies.


### -param NameSize [out, optional]

Receives the size in characters of the name of the pseudo-register.  If <i>NameSize</i> is <b>NULL</b>, this information is not returned.


### -param TypeModule [out, optional]

Receives the base address of the module to which the register's type belongs.  If the type of the register is not known, zero is returned.  If <i>TypeModule</i> is <b>NULL</b>, no information is returned.


### -param TypeId [out, optional]

Receives the type ID of the type within the module returned in <i>TypeModule</i>.  If the type ID is not known, zero is returned.  If <i>TypeId</i> is <b>NULL</b>, no information is returned.


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
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
The description for the register was not available

</td>
</tr>
</table>
 




## -remarks



Descriptions are not always available for all registers.  If a pseudo-register does not have a value - for example, <b>$eventip</b> will not have a value before an event has occurred - or a type cannot be determined for a pseudo-register, this method will return E_FAIL.

For an overview of the <a href="..\dbgeng\nn-dbgeng-idebugregisters.md">IDebugRegisters</a> interface and other register-related methods, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">Registers</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548206">GetPseudoIndexByName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547957">GetNumberPseudoRegisters</a>



<a href="..\dbgeng\nn-dbgeng-idebugregisters2.md">IDebugRegisters2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugRegisters2::GetPseudoDescriptionWide method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


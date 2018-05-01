---
UID: NF:wdtf.ITracing.SetTraceLevel
title: ITracing::SetTraceLevel
author: windows-driver-content
description: The SetTraceLevel method sets the tracing level for an object.
old-location: dtf\itracing_settracelevel.htm
old-project: dtf
ms.assetid: 3b0b43c4-24b9-41e7-9861-6733c79bf40a
ms.author: windowsdriverdev
ms.date: 4/4/2018
ms.keywords: ITracing interface [Windows Device Testing Framework],SetTraceLevel method, ITracing.SetTraceLevel, ITracing::SetTraceLevel, ITracing_e998383b-984d-4f24-b684-06e81e453714.xml, SetTraceLevel, SetTraceLevel method [Windows Device Testing Framework], SetTraceLevel method [Windows Device Testing Framework],ITracing interface, dtf.itracing_settracelevel, wdtf/ITracing::SetTraceLevel
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtf.h
req.include-header: 
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
-	COM
api_location:
-	wdtf.h
api_name:
-	ITracing.SetTraceLevel
product: Windows
targetos: Windows
req.typenames: 
---

# ITracing::SetTraceLevel


## -description


The <b>SetTraceLevel</b> method sets the tracing level for an object. Every object in the WDTF object model should support the <b>SetTraceLevel</b> method


## -parameters




### -param Level [in]

The new <a href="https://msdn.microsoft.com/library/windows/hardware/ff539616">TTraceLevel</a> value for this object.


## -returns



<b>SetTraceLevel</b> returns a standard <b>HRESULT</b> value.




## -remarks



For more information about tracing levels, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539616">TTraceLevel</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff539512">ITracer</a>.

Use the <a href="https://msdn.microsoft.com/d1bc1775-cb0f-468e-938b-b3ed95e80b5b">Trace_Default</a> level to set the object back to the settings that are defined in the registry for the object's co-class.

Because the <a href="https://msdn.microsoft.com/library/windows/hardware/ff538787">IAction</a> interface inherits from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539519">ITracing</a> interface, all WDTF Actions will support <b>SetTraceLevel</b>. All of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539628">WDTF core interfaces</a> should also support this method.

The following code example demonstrates how to use the <b>SetTraceLevel</b> method.

<b>VBScript</b>

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>'
' Get DeviceManagement Action interface for the target
'
Set Action = CDROM.GetInterface("DeviceManagement")
 
If Err.number &lt;&gt; 0 Then
    WScript.Echo Space(4) &amp; "Failed to get interface DeviceManagement. Error Number:" &amp; Err.number
Else            
    '
    ' Set the tracing level to HIGH
    '
    Action.SetTraceLevel(Trace3_High)
    If Err.number &lt;&gt; 0 Then
        WScript.Echo Space(4) &amp; "Failed to set tracing level to 'High'. Error Number:" &amp; Err.number
    End If

    '
    ' Disable the CD-ROM
    '
    WScript.Echo Space(4) &amp; "Trying to disable device..."
 
    Action.Disable()
 
    If Err.number &lt;&gt; 0 Then
        WScript.Echo Space(4) &amp; "Failed to disable the specified CDROM. Error     Number:" &amp; Err.number &amp; vbcrlf
    Else
        WScript.Echo Space(4) &amp; "Specified CDROM successfully disabled." &amp; vbcrlf
    End If
End If</pre>
</td>
</tr>
</table></span></div>
<b>C++</b>

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>IDevMan* pDevMan;        // DeviceManagement Action interface

VARIANT vtEmpty;       // To be passed as a parameter to ITarget::GetInterface
VariantInit(&amp;vtEmpty);

//
// Get DeviceManagement Action interface
//
hr = pCDROM-&gt;GetInterface(L"DeviceManagement", vtEmpty, vtEmpty, (IAction**)(&amp;pDevMan));
if(FAILED(hr))
{
    _tprintf(_T("\n  Failed to get DeviceManagement Interface for specified CDROM Device. Error: 0x%x"), hr);
 goto Cleanup;
}

//
// Set the trace level to High
//
hr = pDevMan-&gt;SetTraceLevel(Trace3_High);
if(FAILED(hr))
{
    _tprintf(_T("\n  Failed to set tracing level to 'High'. Error: 0x%x"), hr);
}
 
//
// Disable the CD-ROM
//
_tprintf(_T("\n  Trying to disable device..."));

hr = pDevMan-&gt;Disable();
if(FAILED(hr))
{
    _tprintf(_T("\n  Failed to disable the specified CDROM. Error: 0x%x"), hr);
}
else
{
    _tprintf(_T("\n  Specified CDROM successfully disabled."));
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539512">ITracer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539519">ITracing</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539616">TTraceLevel</a>
 

 


---
UID: NF:wdtf.ITracing.SetTraceLevel
title: ITracing::SetTraceLevel (wdtf.h)
description: The SetTraceLevel method sets the tracing level for an object.
old-location: dtf\itracing_settracelevel.htm
tech.root: dtf
ms.assetid: 3b0b43c4-24b9-41e7-9861-6733c79bf40a
ms.date: 04/04/2018
ms.keywords: ITracing interface [Windows Device Testing Framework],SetTraceLevel method, ITracing.SetTraceLevel, ITracing::SetTraceLevel, ITracing_e998383b-984d-4f24-b684-06e81e453714.xml, SetTraceLevel, SetTraceLevel method [Windows Device Testing Framework], SetTraceLevel method [Windows Device Testing Framework],ITracing interface, dtf.itracing_settracelevel, wdtf/ITracing::SetTraceLevel
f1_keywords:
 - "wdtf/ITracing.SetTraceLevel"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- wdtf.h
api_name:
- ITracing.SetTraceLevel
product:
- Windows
targetos: Windows
req.typenames: 
---

# ITracing::SetTraceLevel


## -description


The <b>SetTraceLevel</b> method sets the tracing level for an object. Every object in the WDTF object model should support the <b>SetTraceLevel</b> method


## -parameters




### -param Level [in]

The new <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">TTraceLevel</a> value for this object.


## -returns



<b>SetTraceLevel</b> returns a standard <b>HRESULT</b> value.




## -remarks



For more information about tracing levels, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">TTraceLevel</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">ITracer</a>.

Use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Trace_Default</a> level to set the object back to the settings that are defined in the registry for the object's co-class.

Because the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtf/nn-wdtf-iaction">IAction</a> interface inherits from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">ITracing</a> interface, all WDTF Actions will support <b>SetTraceLevel</b>. All of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">WDTF core interfaces</a> should also support this method.

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
 
If Err.number <> 0 Then
    WScript.Echo Space(4) & "Failed to get interface DeviceManagement. Error Number:" & Err.number
Else            
    '
    ' Set the tracing level to HIGH
    '
    Action.SetTraceLevel(Trace3_High)
    If Err.number <> 0 Then
        WScript.Echo Space(4) & "Failed to set tracing level to 'High'. Error Number:" & Err.number
    End If

    '
    ' Disable the CD-ROM
    '
    WScript.Echo Space(4) & "Trying to disable device..."
 
    Action.Disable()
 
    If Err.number <> 0 Then
        WScript.Echo Space(4) & "Failed to disable the specified CDROM. Error     Number:" & Err.number & vbcrlf
    Else
        WScript.Echo Space(4) & "Specified CDROM successfully disabled." & vbcrlf
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
VariantInit(&vtEmpty);

//
// Get DeviceManagement Action interface
//
hr = pCDROM->GetInterface(L"DeviceManagement", vtEmpty, vtEmpty, (IAction**)(&pDevMan));
if(FAILED(hr))
{
    _tprintf(_T("\n  Failed to get DeviceManagement Interface for specified CDROM Device. Error: 0x%x"), hr);
 goto Cleanup;
}

//
// Set the trace level to High
//
hr = pDevMan->SetTraceLevel(Trace3_High);
if(FAILED(hr))
{
    _tprintf(_T("\n  Failed to set tracing level to 'High'. Error: 0x%x"), hr);
}
 
//
// Disable the CD-ROM
//
_tprintf(_T("\n  Trying to disable device..."));

hr = pDevMan->Disable();
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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">ITracer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">ITracing</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">TTraceLevel</a>
 

 


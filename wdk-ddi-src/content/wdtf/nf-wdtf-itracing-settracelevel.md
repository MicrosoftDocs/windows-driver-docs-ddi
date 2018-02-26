---
UID: NF:wdtf.ITracing.SetTraceLevel
title: ITracing::SetTraceLevel method
author: windows-driver-content
description: The SetTraceLevel method sets the tracing level for an object.
old-location: dtf\itracing_settracelevel.htm
old-project: dtf
ms.assetid: 3b0b43c4-24b9-41e7-9861-6733c79bf40a
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, ., :, I, ITracing, ITracing interface [Windows Device Testing Framework], SetTraceLevel method, ITracing::SetTraceLevel, ITracing_e998383b-984d-4f24-b684-06e81e453714.xml, L, S, SetTraceLevel method [Windows Device Testing Framework], SetTraceLevel method [Windows Device Testing Framework], ITracing interface, SetTraceLevel,ITracing.SetTraceLevel, T, a, c, dtf.itracing_settracelevel, e, g, i, l, n, r, t, v, wdtf/ITracing::SetTraceLevel"
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
req.lib: wdtf.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	wdtf.h
apiname:
-	ITracing.SetTraceLevel
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# ITracing::SetTraceLevel method


## -description


The <b>SetTraceLevel</b> method sets the tracing level for an object. Every object in the WDTF object model should support the <b>SetTraceLevel</b> method


## -syntax


````
HRESULT SetTraceLevel(
  [in] TTraceLevel Level
);
````


## -parameters




### -param Level [in]

The new <a href="..\wdtf\ne-wdtf-__midl___midl_itf_wdtf_0000_0001_0001.md">TTraceLevel</a> value for this object.


## -returns



<b>SetTraceLevel</b> returns a standard <b>HRESULT</b> value.




## -remarks



For more information about tracing levels, see <a href="..\wdtf\ne-wdtf-__midl___midl_itf_wdtf_0000_0001_0001.md">TTraceLevel</a> and <a href="..\wdtf\nn-wdtf-itracer.md">ITracer</a>.

Use the <a href="..\wdtf\ne-wdtf-__midl___midl_itf_wdtf_0000_0001_0001.md">Trace_Default</a> level to set the object back to the settings that are defined in the registry for the object's co-class.

Because the <a href="https://msdn.microsoft.com/library/windows/hardware/ff538787">IAction</a> interface inherits from the <a href="..\wdtf\nn-wdtf-itracing.md">ITracing</a> interface, all WDTF Actions will support <b>SetTraceLevel</b>. All of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539628">WDTF core interfaces</a> should also support this method.

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

<a href="..\wdtf\nn-wdtf-itracing.md">ITracing</a>



<a href="..\wdtf\ne-wdtf-__midl___midl_itf_wdtf_0000_0001_0001.md">TTraceLevel</a>



<a href="..\wdtf\nn-wdtf-itracer.md">ITracer</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20ITracing::SetTraceLevel method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


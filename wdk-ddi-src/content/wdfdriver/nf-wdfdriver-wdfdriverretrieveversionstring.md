---
UID: NF:wdfdriver.WdfDriverRetrieveVersionString
title: WdfDriverRetrieveVersionString function
author: windows-driver-content
description: The WdfDriverRetrieveVersionString method retrieves a Unicode string that identifies the version of the Kernel-Mode Driver Framework that the driver is running with.
old-location: wdf\wdfdriverretrieveversionstring.htm
old-project: wdf
ms.assetid: cbea7a3c-faae-4779-9a27-6c2b60f2b35c
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DFDriverObjectRef_42298067-6221-4d0c-af6b-8579f95d2047.xml, WdfDriverRetrieveVersionString, WdfDriverRetrieveVersionString method, kmdf.wdfdriverretrieveversionstring, wdf.wdfdriverretrieveversionstring, wdfdriver/WdfDriverRetrieveVersionString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdriver.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfDriverRetrieveVersionString
product: Windows
targetos: Windows
req.typenames: WDF_DRIVER_INIT_FLAGS
req.product: Windows 10 or later.
---

# WdfDriverRetrieveVersionString function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDriverRetrieveVersionString</b> method retrieves a Unicode string that identifies the version of the Kernel-Mode Driver Framework that the driver is running with.


## -syntax


````
NTSTATUS WdfDriverRetrieveVersionString(
  _In_ WDFDRIVER Driver,
  _In_ WDFSTRING String
);
````


## -parameters




### -param Driver [in]

A handle to the driver's framework driver object that the driver obtained from a previous call to <a href="..\wdfdriver\nf-wdfdriver-wdfdrivercreate.md">WdfDriverCreate</a> or <a href="..\wdfdriver\nf-wdfdriver-wdfgetdriver.md">WdfGetDriver</a>.


### -param String [in]

A handle to a framework string object that the driver obtained from a previous call to <a href="..\wdfstring\nf-wdfstring-wdfstringcreate.md">WdfStringCreate</a>. The framework assigns the version string to the string object.


## -returns



<b>WdfDriverRetrieveVersionString</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The framework could not allocate a buffer for the Unicode string.

</td>
</tr>
</table>
 

This method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A system bug check occurs if the <i>Driver</i> handle is invalid.




## -remarks



Your driver can call <b>WdfDriverRetrieveVersionString</b> if you want to display a string that identifies the framework library's version. The string's format might change from one version to another, so the driver must not attempt to interpret the string's format or content.

For more information about library versions, see <a href="https://msdn.microsoft.com/51db6f3c-45cb-46a7-9dd4-2bab67893fea">Framework Library Versioning</a>.


#### Examples

The following code example creates a string object, assigns the version string to the object, and displays the string if a debugger is running.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDFSTRING string;
UNICODE_STRING us;

status = WdfStringCreate(
                         NULL,
                         WDF_NO_OBJECT_ATTRIBUTES,
                         &amp;string
                         );
if (NT_SUCCESS(status)) {
    status = WdfDriverRetrieveVersionString(
                                            driver,
                                            string
                                            );
    if (NT_SUCCESS(status)) {
        WdfStringGetUnicodeString(
                                  string,
                                  &amp;us
                                  );
        DbgPrint(
                 "WDF Version string:  %wZ\n",
                 &amp;us
                 );
    }
    WdfObjectDelete(string);
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfstring\nf-wdfstring-wdfstringgetunicodestring.md">WdfStringGetUnicodeString</a>



<a href="..\wdfobject\nf-wdfobject-wdfobjectdelete.md">WdfObjectDelete</a>



<a href="..\wdfdriver\nf-wdfdriver-wdfdriverisversionavailable.md">WdfDriverIsVersionAvailable</a>



<a href="..\wdfdriver\nf-wdfdriver-wdfgetdriver.md">WdfGetDriver</a>



<a href="..\wdfstring\nf-wdfstring-wdfstringcreate.md">WdfStringCreate</a>



<a href="..\wdfdriver\nf-wdfdriver-wdfdrivercreate.md">WdfDriverCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDriverRetrieveVersionString method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


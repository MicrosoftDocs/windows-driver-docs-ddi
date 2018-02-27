---
UID: NF:wdfregistry.WdfRegistryRemoveValue
title: WdfRegistryRemoveValue function
author: windows-driver-content
description: The WdfRegistryRemoveValue method removes a specified value and its data from a specified registry key.
old-location: wdf\wdfregistryremovevalue.htm
old-project: wdf
ms.assetid: 485583b2-2736-4ecf-b58c-65b4d4f47a20
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DFRegKeyObjectRef_2928cd6b-7fb0-46aa-bcc4-4def625bb2fe.xml, WdfRegistryRemoveValue, WdfRegistryRemoveValue method, kmdf.wdfregistryremovevalue, wdf.wdfregistryremovevalue, wdfregistry/WdfRegistryRemoveValue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfregistry.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfRegistryRemoveValue
product: Windows
targetos: Windows
req.typenames: WDF_QUERY_INTERFACE_CONFIG, *PWDF_QUERY_INTERFACE_CONFIG
req.product: Windows 10 or later.
---

# WdfRegistryRemoveValue function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRegistryRemoveValue</b> method removes a specified value and its data from a specified registry key.


## -syntax


````
NTSTATUS WdfRegistryRemoveValue(
  _In_ WDFKEY           Key,
  _In_ PCUNICODE_STRING ValueName
);
````


## -parameters




### -param Key [in]

A handle to a registry-key object that represents an opened registry key.


### -param ValueName [in]

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains a value name. 


## -returns



<b>WdfRegistryRemoveValue</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, the method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">

<a href="..\wdfregistry\nf-wdfregistry-wdfregistryremovevalue.md">WdfRegistryRemoveValue</a> was not called at IRQL = PASSIVE_LEVEL. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was specified.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The driver did not open the registry key with KEY_SET_VALUE access.

</td>
</tr>
</table>
 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



For more information about registry-key objects, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">Using the Registry in Framework-Based Drivers</a>.


#### Examples

The following code example removes the <b>MyValue</b> value and its data from a specified registry key.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>DECLARE_CONST_UNICODE_STRING(valueName, L"MyValue");

status = WdfRegistryRemoveValue(
                                Key,
                                &amp;valueName
                                );</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRegistryRemoveValue method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


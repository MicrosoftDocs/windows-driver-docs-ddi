---
UID: NF:wdfobject.WdfObjectContextGetObject
title: WdfObjectContextGetObject function
author: windows-driver-content
description: The WdfObjectContextGetObject method returns a handle to the framework object that a specified context space belongs to.
old-location: wdf\wdfobjectcontextgetobject.htm
old-project: wdf
ms.assetid: 7288a7e5-8e64-4ac3-9779-edc27a3888bb
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: kmdf.wdfobjectcontextgetobject, DFGenObjectRef_cf11ce54-dbb0-4835-919d-6f0bec903e2d.xml, wdf.wdfobjectcontextgetobject, WdfObjectContextGetObject, WdfObjectContextGetObject method, wdfobject/WdfObjectContextGetObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfobject.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: Any level
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
-	WdfObjectContextGetObject
product: Windows
targetos: Windows
req.typenames: WDF_SYNCHRONIZATION_SCOPE
req.product: Windows 10 or later.
---

# WdfObjectContextGetObject function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfObjectContextGetObject</b> method returns a handle to the framework object that a specified context space belongs to.


## -syntax


````
WDFOBJECT WdfObjectContextGetObject(
  _In_ PVOID ContextPointer
);
````


## -parameters




### -param ContextPointer [in]

A pointer to object context space. The driver can obtain this pointer by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff548749">WdfObjectGetTypedContext</a>.


## -returns



<b>WdfObjectContextGetObject</b> returns a handle to a framework object. 




## -remarks



For more information about object context space, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/framework-object-context-space">Framework Object Context Space</a>. 


#### Examples

The following code example obtains a handle to the framework object that a specified context space belongs to.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDFDEVICE  device;

device = WdfObjectContextGetObject(DeviceContext);</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548749">WdfObjectGetTypedContext</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfObjectContextGetObject method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


---
UID: NS:wdfobject._WDF_OBJECT_ATTRIBUTES
title: "_WDF_OBJECT_ATTRIBUTES"
author: windows-driver-content
description: The WDF_OBJECT_ATTRIBUTES structure describes attributes that can be associated with any framework object.
old-location: wdf\wdf_object_attributes.htm
old-project: wdf
ms.assetid: 3331c2d8-3100-410d-9c75-33a3b55d5a49
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: kmdf.wdf_object_attributes, *PWDF_OBJECT_ATTRIBUTES, WDF_OBJECT_ATTRIBUTES structure, WDF_OBJECT_ATTRIBUTES, DFGenObjectRef_cfd7583f-13f6-4755-85d4-7a08401d0ea7.xml, PWDF_OBJECT_ATTRIBUTES, wdf.wdf_object_attributes, wdfobject/WDF_OBJECT_ATTRIBUTES, _WDF_OBJECT_ATTRIBUTES, wdfobject/PWDF_OBJECT_ATTRIBUTES, PWDF_OBJECT_ATTRIBUTES structure pointer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdfobject.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfobject.h
apiname:
-	WDF_OBJECT_ATTRIBUTES
product: Windows
targetos: Windows
req.typenames: "*PWDF_OBJECT_ATTRIBUTES, WDF_OBJECT_ATTRIBUTES"
req.product: Windows 10 or later.
---

# _WDF_OBJECT_ATTRIBUTES structure


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The WDF_OBJECT_ATTRIBUTES structure describes attributes that can be associated with any framework object.


## -syntax


````
typedef struct _WDF_OBJECT_ATTRIBUTES {
  ULONG                          Size;
  PFN_WDF_OBJECT_CONTEXT_CLEANUP EvtCleanupCallback;
  PFN_WDF_OBJECT_CONTEXT_DESTROY EvtDestroyCallback;
  WDF_EXECUTION_LEVEL            ExecutionLevel;
  WDF_SYNCHRONIZATION_SCOPE      SynchronizationScope;
  WDFOBJECT                      ParentObject;
  size_t                         ContextSizeOverride;
  PCWDF_OBJECT_CONTEXT_TYPE_INFO ContextTypeInfo;
} WDF_OBJECT_ATTRIBUTES, *PWDF_OBJECT_ATTRIBUTES;
````


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field EvtCleanupCallback

A pointer to the driver's <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_cleanup.md">EvtCleanupCallback</a> callback function, or <b>NULL</b>.


### -field EvtDestroyCallback

A pointer to the driver's <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_destroy.md">EvtDestroyCallback</a> callback function, or <b>NULL</b>.


### -field ExecutionLevel

A <a href="..\wdfobject\ne-wdfobject-_wdf_execution_level.md">WDF_EXECUTION_LEVEL</a>-typed value that specifies the maximum IRQL at which the framework will call the object's event callback functions. For a list of framework objects for which the driver can specify an <b>ExecutionLevel</b> value, see <a href="..\wdfobject\ne-wdfobject-_wdf_execution_level.md">WDF_EXECUTION_LEVEL</a>.


### -field SynchronizationScope

A <a href="..\wdfobject\ne-wdfobject-_wdf_synchronization_scope.md">WDF_SYNCHRONIZATION_SCOPE</a>-typed value that specifies how the framework will synchronize execution of the object's event callback functions. For a list of framework objects for which the driver can specify a <b>SynchronizationScope</b> value, see <a href="..\wdfobject\ne-wdfobject-_wdf_synchronization_scope.md">WDF_SYNCHRONIZATION_SCOPE</a>.


### -field ParentObject

A handle to the object's parent object, or <b>NULL</b> if the object does not have a driver-specified parent. 

See <a href="https://msdn.microsoft.com/799284a5-91c0-47b0-8f20-75a5f8e2284d">Summary of Framework Objects</a> for a table that shows the objects that allow a driver-specified parent. The table also shows the default parent of each object. 


### -field ContextSizeOverride

If not zero, this value overrides the <b>ContextSize</b> member of the <a href="..\wdfobject\ns-wdfobject-_wdf_object_context_type_info.md">WDF_OBJECT_CONTEXT_TYPE_INFO</a> structure that the <b>ContextTypeInfo</b> member references. This value is optional and can be zero. If the value is not zero, it must specify a size, in bytes, that is larger than the value that is specified for the <b>ContextSize</b> member of the WDF_OBJECT_CONTEXT_TYPE_INFO structure. For more information, see the following Remarks section.


### -field ContextTypeInfo

A pointer to a <a href="..\wdfobject\ns-wdfobject-_wdf_object_context_type_info.md">WDF_OBJECT_CONTEXT_TYPE_INFO</a> structure. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff552405">WDF_OBJECT_ATTRIBUTES_SET_CONTEXT_TYPE</a> macro sets this pointer.


## -remarks



The WDF_OBJECT_ATTRIBUTES structure is used as an input argument to several methods that create framework objects.

To initialize a WDF_OBJECT_ATTRIBUTES structure, the driver must call <a href="..\wdfobject\nf-wdfobject-wdf_object_attributes_init.md">WDF_OBJECT_ATTRIBUTES_INIT</a>. 

Additionally, if you are defining object-specific context information for an object, you must use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552405">WDF_OBJECT_ATTRIBUTES_SET_CONTEXT_TYPE</a> macro. 

Alternatively, you can use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552404">WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE</a> macro instead of the WDF_OBJECT_ATTRIBUTES_INIT and WDF_OBJECT_ATTRIBUTES_SET_CONTEXT_TYPE macros.

For more information about using these macros, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/framework-object-context-space">Framework Object Context Space</a>.

Use the <b>ContextSizeOverride</b> member of WDF_OBJECT_ATTRIBUTES if you want to create <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/framework-object-context-space">object context space</a> that has a variable length. For example, you might define a context space structure that contains an array, as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _MY_REQUEST_CONTEXT {
  ULONG  ByteCount;
  BYTE  Bytes[1];
} MY_REQUEST_CONTEXT, *PMY_REQUEST_CONTEXT;

WDF_DECLARE_CONTEXT_TYPE(MY_REQUEST_CONTEXT);</pre>
</td>
</tr>
</table></span></div>
When your driver creates an object that uses the context space structure, it can use the <b>ContextSizeOverride</b> member to specify the context size that is needed for each individual object. For example, your driver might calculate the number of bytes that are needed in the array from the preceding example and then use <b>ContextSizeOverride</b> to specify the extra bytes, as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_OBJECT_ATTRIBUTES MyRequestObjectAttributes;
PMY_REQUEST_CONTEXT pMyContext;

WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(
                                        &amp;MyRequestObjectAttributes,
                                        MY_REQUEST_CONTEXT
                                        );
MyRequestObjectAttributes.ContextSizeOverride =
                          sizeof(MY_REQUEST_CONTEXT) + Num_Extra_Bytes - 1;</pre>
</td>
</tr>
</table></span></div>
The driver can then create an object with a customized context size.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>status = WdfRequestCreate(
                          &amp;MyRequestObjectAttributes,
                          ioTarget,
                          &amp;newRequest
                          );</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfobject\nf-wdfobject-wdf_object_attributes_init.md">WDF_OBJECT_ATTRIBUTES_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552405">WDF_OBJECT_ATTRIBUTES_SET_CONTEXT_TYPE</a>



<a href="..\wdfobject\nf-wdfobject-wdfobjectallocatecontext.md">WdfObjectAllocateContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552404">WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_OBJECT_ATTRIBUTES structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


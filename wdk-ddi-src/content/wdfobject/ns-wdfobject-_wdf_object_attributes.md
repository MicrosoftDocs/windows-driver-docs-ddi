---
UID: NS:wdfobject._WDF_OBJECT_ATTRIBUTES
title: "_WDF_OBJECT_ATTRIBUTES" (wdfobject.h)
description: The WDF_OBJECT_ATTRIBUTES structure describes attributes that can be associated with any framework object.
old-location: wdf\wdf_object_attributes.htm
tech.root: wdf
ms.assetid: 3331c2d8-3100-410d-9c75-33a3b55d5a49
ms.date: 02/26/2018
ms.keywords: "*PWDF_OBJECT_ATTRIBUTES, DFGenObjectRef_cfd7583f-13f6-4755-85d4-7a08401d0ea7.xml, PWDF_OBJECT_ATTRIBUTES, PWDF_OBJECT_ATTRIBUTES structure pointer, WDF_OBJECT_ATTRIBUTES, WDF_OBJECT_ATTRIBUTES structure, _WDF_OBJECT_ATTRIBUTES, kmdf.wdf_object_attributes, wdf.wdf_object_attributes, wdfobject/PWDF_OBJECT_ATTRIBUTES, wdfobject/WDF_OBJECT_ATTRIBUTES"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfobject.h
api_name:
-	WDF_OBJECT_ATTRIBUTES
product:
- Windows
targetos: Windows
req.typenames: WDF_OBJECT_ATTRIBUTES, *PWDF_OBJECT_ATTRIBUTES
---

# _WDF_OBJECT_ATTRIBUTES structure


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The WDF_OBJECT_ATTRIBUTES structure describes attributes that can be associated with any framework object.


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field EvtCleanupCallback

A pointer to the driver's <a href="https://msdn.microsoft.com/aba2efca-7d1f-4594-af65-13356f0e3f8b">EvtCleanupCallback</a> callback function, or <b>NULL</b>.


### -field EvtDestroyCallback

A pointer to the driver's <a href="https://msdn.microsoft.com/4c3b08d2-bb25-40bd-b2fc-1b9ea2d452b3">EvtDestroyCallback</a> callback function, or <b>NULL</b>.


### -field ExecutionLevel

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff551310">WDF_EXECUTION_LEVEL</a>-typed value that specifies the maximum IRQL at which the framework will call the object's event callback functions. For a list of framework objects for which the driver can specify an <b>ExecutionLevel</b> value, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff551310">WDF_EXECUTION_LEVEL</a>.


### -field SynchronizationScope

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff552518">WDF_SYNCHRONIZATION_SCOPE</a>-typed value that specifies how the framework will synchronize execution of the object's event callback functions. For a list of framework objects for which the driver can specify a <b>SynchronizationScope</b> value, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552518">WDF_SYNCHRONIZATION_SCOPE</a>.


### -field ParentObject

A handle to the object's parent object, or <b>NULL</b> if the object does not have a driver-specified parent. 

See <a href="https://msdn.microsoft.com/799284a5-91c0-47b0-8f20-75a5f8e2284d">Summary of Framework Objects</a> for a table that shows the objects that allow a driver-specified parent. The table also shows the default parent of each object. 


### -field ContextSizeOverride

If not zero, this value overrides the <b>ContextSize</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552407">WDF_OBJECT_CONTEXT_TYPE_INFO</a> structure that the <b>ContextTypeInfo</b> member references. This value is optional and can be zero. If the value is not zero, it must specify a size, in bytes, that is larger than the value that is specified for the <b>ContextSize</b> member of the WDF_OBJECT_CONTEXT_TYPE_INFO structure. For more information, see the following Remarks section.


### -field ContextTypeInfo

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552407">WDF_OBJECT_CONTEXT_TYPE_INFO</a> structure. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff552405">WDF_OBJECT_ATTRIBUTES_SET_CONTEXT_TYPE</a> macro sets this pointer.


## -remarks



The WDF_OBJECT_ATTRIBUTES structure is used as an input argument to several methods that create framework objects.

To initialize a WDF_OBJECT_ATTRIBUTES structure, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff552402">WDF_OBJECT_ATTRIBUTES_INIT</a>. 

Additionally, if you are defining object-specific context information for an object, you must use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552405">WDF_OBJECT_ATTRIBUTES_SET_CONTEXT_TYPE</a> macro. 

Alternatively, you can use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552404">WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE</a> macro instead of the WDF_OBJECT_ATTRIBUTES_INIT and WDF_OBJECT_ATTRIBUTES_SET_CONTEXT_TYPE macros.

For more information about using these macros, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-context-space">Framework Object Context Space</a>.

Use the <b>ContextSizeOverride</b> member of WDF_OBJECT_ATTRIBUTES if you want to create <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-context-space">object context space</a> that has a variable length. For example, you might define a context space structure that contains an array, as follows:

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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552402">WDF_OBJECT_ATTRIBUTES_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552404">WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552405">WDF_OBJECT_ATTRIBUTES_SET_CONTEXT_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548723">WdfObjectAllocateContext</a>
 

 


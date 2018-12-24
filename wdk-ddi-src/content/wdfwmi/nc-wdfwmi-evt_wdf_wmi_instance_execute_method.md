---
UID: NC:wdfwmi.EVT_WDF_WMI_INSTANCE_EXECUTE_METHOD
title: EVT_WDF_WMI_INSTANCE_EXECUTE_METHOD
description: A driver's EvtWmiInstanceExecuteMethod callback function executes a specified method that the driver provides for a WMI data provider's instance.
old-location: wdf\evtwmiinstanceexecutemethod.htm
tech.root: wdf
ms.assetid: b14de1d7-0df2-46d1-a3bd-c23f33d3ed75
ms.date: 02/26/2018
ms.keywords: DFWMIRef_d54dc0b0-bdef-40a7-b863-5946f4d8e5f5.xml, EVT_WDF_WMI_INSTANCE_EXECUTE_METHOD, EVT_WDF_WMI_INSTANCE_EXECUTE_METHOD callback, EvtWmiInstanceExecuteMethod, EvtWmiInstanceExecuteMethod callback function, kmdf.evtwmiinstanceexecutemethod, wdf.evtwmiinstanceexecutemethod, wdfwmi/EvtWmiInstanceExecuteMethod
ms.topic: callback
req.header: wdfwmi.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	WdfWMI.h
api_name:
-	EvtWmiInstanceExecuteMethod
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_WMI_INSTANCE_EXECUTE_METHOD callback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

A driver's <i>EvtWmiInstanceExecuteMethod</i> callback function executes a specified method that the driver provides for a WMI data provider's instance.


## -parameters




### -param WmiInstance [in]

A handle to a WMI instance object.


### -param MethodId [in]

A value that identifies a method in a provider instance. This value corresponds to the <a href="https://msdn.microsoft.com/e2d281b3-913c-43ad-921c-80dc8be09aa0">WmiMethodId</a> value that is specified in the provider's MOF file.


### -param InBufferSize [in]

The number of bytes of input data.


### -param OutBufferSize [in]

The number of bytes of output data that the buffer that <i>Buffer</i> points to can hold.


### -param Buffer [in, out]

A pointer to a buffer that is used for input, output, or both, as determined by the specified method. If both input and output data are provided, the driver overwrites the input data with the output data.


### -param BufferUsed [out]

A pointer to a location that receives the number of bytes that the driver wrote into the output buffer. If the output buffer size that the <i>OutBufferSize</i> parameter specifies is too small, the driver sets this location to the required buffer size.  


## -returns



The <i>EvtWmiInstanceExecuteMethod</i> callback function must return STATUS_SUCCESS if the operation succeeds. Otherwise, this function must return a status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>FALSE</b>. The driver must return STATUS_BUFFER_TOO_SMALL if the value of the <i>OutBufferSize</i> parameter indicates that the output buffer is too small to receive the data.




## -remarks



To register an <i>EvtWmiInstanceExecuteMethod</i> callback function, your driver must place the function's address in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553058">WDF_WMI_INSTANCE_CONFIG</a> structure before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff551178">WdfWmiInstanceCreate</a>. 

After a driver executes the instance method that the <i>MethodId</i> parameter specifies, the driver must use the <i>BufferUsed</i> parameter to store the number of bytes that were written to the buffer.

The framework does not synchronize calls to a driver's WMI event callback functions with each other or with any of the driver's other event callback functions. If an <i>EvtWmiInstanceExecuteMethod</i> callback function's data is dynamic and shared with other callback functions, your driver can use the framework's <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-framework-locks">wait locks or spin locks</a> to synchronize access to the data.

For more information about the <i>EvtWmiInstanceExecuteMethod</i> callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-wmi-in-kmdf-drivers">Supporting WMI in Framework-Based Drivers</a>.


#### Examples

To define an <i>EvtWmiInstanceExecuteMethod</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtWmiInstanceExecuteMethod</i> callback function that is named <i>MyWmiInstanceExecuteMethod</i>, use the <b>EVT_WDF_WMI_INSTANCE_EXECUTE_METHOD</b> type as shown in this code example:

To define an <i>EvtWmiInstanceExecuteMethod</i> callback function that is named <b>MyWmiInstanceExecuteMethod</b>, you must first provide a function declaration that SDV and other verification tools require, as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_WMI_INSTANCE_EXECUTE_METHOD  MyWmiInstanceExecuteMethod;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
NTSTATUS
 MyWmiInstanceExecuteMethod (
    WDFWMIINSTANCE  WmiInstance,
    ULONG  MethodId,
    ULONG  InBufferSize,
    ULONG  OutBufferSize,
    PVOID  Buffer,
    PULONG  BufferUsed
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_WMI_INSTANCE_EXECUTE_METHOD</b> function type is defined in the WdfWMI.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_WMI_INSTANCE_EXECUTE_METHOD</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also




<a href="https://msdn.microsoft.com/13eed838-2943-4bb4-915f-6a84f0f95851">EvtWmiInstanceQueryInstance</a>



<a href="https://msdn.microsoft.com/defd33c5-90ae-40c9-9123-7c3de2c77f35">EvtWmiInstanceSetInstance</a>



<a href="https://msdn.microsoft.com/3011d92c-b12b-4240-8a4e-aa039ab8e053">EvtWmiInstanceSetItem</a>



<a href="https://msdn.microsoft.com/89b48747-d3aa-48c7-825c-94545f378f07">EvtWmiProviderFunctionControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553058">WDF_WMI_INSTANCE_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551178">WdfWmiInstanceCreate</a>
 

 


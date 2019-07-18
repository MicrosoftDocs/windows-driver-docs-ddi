---
UID: NC:wmilib.WMI_EXECUTE_METHOD_CALLBACK
title: WMI_EXECUTE_METHOD_CALLBACK (wmilib.h)
description: The DpWmiExecuteMethod routine executes a method associated with a data block. This routine is optional.
old-location: kernel\dpwmiexecutemethod.htm
tech.root: kernel
ms.assetid: 3e671484-8f8d-4ba0-a763-37c3178487ca
ms.date: 04/30/2018
ms.keywords: DpWmiExecuteMethod, DpWmiExecuteMethod callback function [Kernel-Mode Driver Architecture], WMI_EXECUTE_METHOD_CALLBACK, WMI_EXECUTE_METHOD_CALLBACK callback, k903_b641484a-8f32-440d-8efc-76293ddeec2c.xml, kernel.dpwmiexecutemethod, wmilib/DpWmiExecuteMethod
ms.topic: callback
f1_keywords:
 - "wmilib/DpWmiExecuteMethod"
req.header: wmilib.h
req.include-header: Wmilib.h
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
req.irql: Called at PASSIVE_LEVEL.
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wmilib.h
api_name:
- DpWmiExecuteMethod
product:
- Windows
targetos: Windows
req.typenames: 
---

# WMI_EXECUTE_METHOD_CALLBACK callback function


## -description


The <i>DpWmiExecuteMethod</i> routine executes a method associated with a data block. This routine is optional.


## -parameters




### -param DeviceObject [in]

Pointer to the driver's WDM <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure.


### -param Irp [in]

Pointer to the IRP.


### -param GuidIndex [in]

Specifies the data block by supplying a zero-based index into the list of GUIDs that the driver provided in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wmilib/ns-wmilib-_wmilib_context">WMILIB_CONTEXT</a> structure it passed to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wmilib/nf-wmilib-wmisystemcontrol">WmiSystemControl</a>. 


### -param InstanceIndex [in]

If the block specified by <i>GuidIndex</i> has multiple instances, <i>InstanceIndex</i> specifies a zero-based index value that identifies the instance.


### -param MethodId [in]

Specifies the ID of the method to execute. The driver defines the method ID as an item in a data block.


### -param InBufferSize [in]

Indicates the size in bytes of the input data. If there is no input data, <i>InBufferSize</i> is zero. 


### -param OutBufferSize [in]

Indicates the number of bytes available in the buffer for output data.


### -param Buffer [in, out]

Pointer to a buffer that holds input data, if any, and receives output data, if any, for the method. If the buffer is too small to receive all of the output data, the driver returns STATUS_BUFFER_TOO_SMALL and calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wmilib/nf-wmilib-wmicompleterequest">WmiCompleteRequest</a> with the size required.


## -returns



<i>DpWmiExecuteMethod</i> returns STATUS_SUCCESS or an appropriate error code such as the following:




## -remarks



WMI calls a driver's <i>DpWmiExecuteMethod</i> routine after the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wmilib/nf-wmilib-wmisystemcontrol">WmiSystemControl</a> in response to an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-execute-method">IRP_MN_EXECUTE_METHOD</a> request.

If a driver implements a <i>DpWmiExecuteMethod</i> routine, the driver must place the routine's address in the <b>ExecuteWmiMethod</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wmilib/ns-wmilib-_wmilib_context">WMILIB_CONTEXT</a> structure that it passes to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wmilib/nf-wmilib-wmisystemcontrol">WmiSystemControl</a>. If a driver does not implement a <i>DpWmiExecuteMethod</i> routine, it must set <b>ExecuteWmiMethod</b> to <b>NULL</b>. In the latter case, WMI returns STATUS_INVALID_DEVICE_REQUEST to the caller in response to any <b>IRP_MN_EXECUTE_METHOD</b> request.

The driver is responsible for validating all input arguments. Specifically, the driver must do the following:

<ul>
<li>
Verify that the <i>GuidIndex</i> value is between zero and GuidCount-1, based on the <b>GuidCount</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wmilib/ns-wmilib-_wmilib_context">WMILIB_CONTEXT</a> structure.

</li>
<li>
Verify that the driver has not flagged the specified data block for removal. If the driver recently specified the WMIREG_FLAG_REMOVE_GUID flag in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wmilib/ns-wmilib-_wmiguidreginfo">WMIGUIDREGINFO</a> structure that is contained in a <b>WMILIB_CONTEXT</b> structure, it is possible for an additional request to arrive before the removal occurs.

</li>
<li>
Verify that the <i>InstanceIndex</i> value is within the range of instance indexes that are supported by the driver for the data block. 

</li>
<li>
Verify that the method identifier supplied by <i>MethodId</i> is a valid identifier for the specified data block, and that the caller is allowed to execute the method.

</li>
<li>
Verify that <i>Buffer</i> and <i>InBufferSize</i> describe a buffer that is large enough to contain the specified method's input parameters, including padding if necessary, and verify that the input parameters are valid. 

</li>
<li>
Verify that <i>Buffer</i> and <i>OutBufferSize</i> describe a buffer that is large enough to receive the specified method's output data, including padding if necessary.

</li>
</ul>
Do not assume the thread context is that of the initiating user-mode application—a higher-level driver might have changed it.

If the specified method performs an operation that causes data loss, such as fetching and resetting the contents of a set of counters, the driver should validate the output buffer size before performing the operation. That way, the driver can return STATUS_BUFFER_TOO_SMALL and allow the caller to resubmit the request with a larger buffer, without prematurely resetting the counters.

After executing the method and writing any output data to the buffer, the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wmilib/nf-wmilib-wmicompleterequest">WmiCompleteRequest</a> to complete the request.

This routine can be pageable.

For more information about implementing this routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/calling-wmisystemcontrol-to-handle-wmi-irps">Calling WmiSystemControl to Handle WMI IRPs</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-execute-method">IRP_MN_EXECUTE_METHOD</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wmilib/ns-wmilib-_wmilib_context">WMILIB_CONTEXT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wmilib/nf-wmilib-wmicompleterequest">WmiCompleteRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wmilib/nf-wmilib-wmisystemcontrol">WmiSystemControl</a>
 

 


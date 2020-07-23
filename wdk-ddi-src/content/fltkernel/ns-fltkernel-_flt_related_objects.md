---
UID: NS:fltkernel._FLT_RELATED_OBJECTS
title: _FLT_RELATED_OBJECTS (fltkernel.h)
description: The FLT_RELATED_OBJECTS structure contains opaque pointers for the objects associated with an operation.
old-location: ifsk\flt_related_objects.htm
tech.root: ifsk
ms.assetid: dd1730f5-58ff-4d0d-9a00-17cd1fe36c5f
ms.date: 04/16/2018
keywords: ["_FLT_RELATED_OBJECTS structure"]
ms.keywords: "*PFLT_RELATED_OBJECTS, FLT_RELATED_OBJECTS, FLT_RELATED_OBJECTS structure [Installable File System Drivers], FltSystemStructures_24fcdf06-9d2e-41bf-89f8-08cb37782089.xml, PFLT_RELATED_OBJECTS, PFLT_RELATED_OBJECTS structure pointer [Installable File System Drivers], _FLT_RELATED_OBJECTS, fltkernel/FLT_RELATED_OBJECTS, fltkernel/PFLT_RELATED_OBJECTS, ifsk.flt_related_objects"
f1_keywords:
 - "fltkernel/FLT_RELATED_OBJECTS"
 - "FLT_RELATED_OBJECTS"
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Windows
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
- HeaderDef
api_location:
- fltkernel.h
api_name:
- FLT_RELATED_OBJECTS
targetos: Windows
req.typenames: FLT_RELATED_OBJECTS, *PFLT_RELATED_OBJECTS
---

# _FLT_RELATED_OBJECTS structure


## -description


The FLT_RELATED_OBJECTS structure contains opaque pointers for the objects associated with an operation. 


## -struct-fields




### -field Size

Size, in bytes, of the FLT_RELATED_OBJECTS structure. 


### -field TransactionContext

Opaque member that contains the transaction miniversion ID value if the <b>Transaction</b> member is not <b>NULL</b>.  If <b>Transaction</b> is <b>NULL</b>, the value of <b>TransactionContext</b> is undefined.


### -field Filter

Opaque filter pointer for the minifilter driver whose callback routine is being called for the operation. This pointer uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded. 


### -field Volume

Opaque volume pointer for the volume that is associated with the operation. This pointer uniquely identifies the volume and remains constant over the lifetime of the volume device stack. 


### -field Instance

Opaque instance pointer for the minifilter driver instance that is associated with the operation. This pointer uniquely identifies the instance and remains constant as long as the instance is attached to a volume. 


### -field FileObject

Pointer to the file object, if any, for the operation. 


### -field Transaction

On Windows Vista and later, this member is an opaque transaction pointer to the transaction that is associated with the operation. The operation will be part of a transaction if the value of this member is not <b>NULL</b>.  If the value of this member is <b>NULL</b>, the operation will not be part of a transaction.  On Windows operating systems before Windows Vista, the value of this member will always be <b>NULL</b>. 


## -remarks



The FLT_RELATED_OBJECTS structure is allocated by the filter manager and contains opaque pointers for the objects associated with an I/O operation or an instance setup or teardown operation. 

The contents of the FLT_RELATED_OBJECTS structure are set by the filter manager. Minifilter drivers cannot directly modify the contents of this structure. However, if a minifilter driver modifies the target instance or target file object for an I/O operation in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_io_parameter_block">FLT_IO_PARAMETER_BLOCK</a> structure for the operation, the filter manager modifies the value of the corresponding <b>Instance</b> or <b>FileObject</b> member of the FLT_RELATED_OBJECTS structure that is passed to lower minifilter drivers. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/modifying-the-parameters-for-an-i-o-operation">Modifying the Parameters for an I/O Operation</a>. 

A minifilter driver receives a pointer to an FLT_RELATED_OBJECTS structure as the <i>FltObjects</i> input parameter to the following callback routine types: 


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_post_operation_callback">PFLT_POST_OPERATION_CALLBACK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_pre_operation_callback">PFLT_PRE_OPERATION_CALLBACK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_instance_setup_callback">PFLT_INSTANCE_SETUP_CALLBACK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_instance_query_teardown_callback">PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_instance_teardown_callback">PFLT_INSTANCE_TEARDOWN_CALLBACK</a>


To retrieve pointers to a minifilter driver's contexts for the objects in an FLT_RELATED_OBJECTS structure, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetcontexts">FltGetContexts</a>. 


<div class="alert"><b>Note</b>  <code>typedef CONST struct _FLT_RELATED_OBJECTS *PCFLT_RELATED_OBJECTS;</code></div>
<div> </div>





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_io_parameter_block">FLT_IO_PARAMETER_BLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_related_contexts">FLT_RELATED_CONTEXTS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdocompletionprocessingwhensafe">FltDoCompletionProcessingWhenSafe</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetcontexts">FltGetContexts</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_instance_query_teardown_callback">PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_instance_setup_callback">PFLT_INSTANCE_SETUP_CALLBACK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_instance_teardown_callback">PFLT_INSTANCE_TEARDOWN_CALLBACK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_post_operation_callback">PFLT_POST_OPERATION_CALLBACK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_pre_operation_callback">PFLT_PRE_OPERATION_CALLBACK</a>
 

 


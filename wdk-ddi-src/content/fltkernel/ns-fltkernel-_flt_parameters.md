---
UID: NS:fltkernel._FLT_PARAMETERS
title: _FLT_PARAMETERS (fltkernel.h)
description: The FLT_PARAMETERS union defines the request-type-specific parameters associated with an I/O operation.
old-location: ifsk\flt_parameters.htm
tech.root: ifsk
ms.assetid: 62aa20b7-ce5c-4d42-bce2-1d76a98887ed
ms.date: 04/16/2018
ms.keywords: "*PFLT_PARAMETERS, FLT_PARAMETERS, FLT_PARAMETERS union [Installable File System Drivers], FltSystemStructures_2ebb0ec7-76cc-49a3-b2ec-186f67369bbb.xml, PFLT_PARAMETERS, PFLT_PARAMETERS union pointer [Installable File System Drivers], _FLT_PARAMETERS, fltkernel/FLT_PARAMETERS, fltkernel/PFLT_PARAMETERS, ifsk.flt_parameters"
ms.topic: struct
f1_keywords:
 - "fltkernel/FLT_PARAMETERS"
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
- FLT_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: FLT_PARAMETERS, *PFLT_PARAMETERS
---

# _FLT_PARAMETERS structure


## -description


The FLT_PARAMETERS union defines the request-type-specific parameters associated with an I/O operation. 


## -struct-fields


## -remarks



This structure is stored in the <b>Parameters</b> field of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_io_parameter_block">FLT_IO_PARAMETER_BLOCK</a> structure for the operation. (A pointer to the FLT_IO_PARAMETER_BLOCK structure is stored in the <b>Iopb</b> field of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a> structure for the operation.) 

For the specific FLT_PARAMETERS union component used in each type of I/O operation, see the following reference entries. 


<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-create">FLT_PARAMETERS for IRP_MJ_CREATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-device-control-and-irp-mj-internal-device-co">FLT_PARAMETERS for IRP_MJ_DEVICE_CONTROL and IRP_MJ_INTERNAL_DEVICE_CONTROL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-directory-control">FLT_PARAMETERS for IRP_MJ_DIRECTORY_CONTROL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-file-system-control">FLT_PARAMETERS for IRP_MJ_FILE_SYSTEM_CONTROL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-lock-control">FLT_PARAMETERS for IRP_MJ_LOCK_CONTROL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-pnp">FLT_PARAMETERS for IRP_MJ_PNP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-query-ea">FLT_PARAMETERS for IRP_MJ_QUERY_EA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-query-information">FLT_PARAMETERS for IRP_MJ_QUERY_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-query-quota">FLT_PARAMETERS for IRP_MJ_QUERY_QUOTA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-query-security">FLT_PARAMETERS for IRP_MJ_QUERY_SECURITY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-query-volume-information">FLT_PARAMETERS for IRP_MJ_QUERY_VOLUME_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-read">FLT_PARAMETERS for IRP_MJ_READ</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-set-ea">FLT_PARAMETERS for IRP_MJ_SET_EA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-set-information">FLT_PARAMETERS for IRP_MJ_SET_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-set-quota">FLT_PARAMETERS for IRP_MJ_SET_QUOTA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-set-security">FLT_PARAMETERS for IRP_MJ_SET_SECURITY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-set-volume-information">FLT_PARAMETERS for IRP_MJ_SET_VOLUME_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-write">FLT_PARAMETERS for IRP_MJ_WRITE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-acquire-for-mod-write">FLT_PARAMETERS for IRP_MJ_ACQUIRE_FOR_MOD_WRITE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-acquire-for-section-synchronization">FLT_PARAMETERS for IRP_MJ_ACQUIRE_FOR_SECTION_SYNCHRONIZATION</a>

[FLT_PARAMETERS for IRP_MJ_QUERY_OPEN](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-query-open)

<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-fast-io-check-if-possible">FLT_PARAMETERS for IRP_MJ_FAST_IO_CHECK_IF_POSSIBLE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-mdl-read">FLT_PARAMETERS for IRP_MJ_MDL_READ</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-mdl-read-complete">FLT_PARAMETERS for IRP_MJ_MDL_READ_COMPLETE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-mdl-write-complete">FLT_PARAMETERS for IRP_MJ_MDL_WRITE_COMPLETE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-network-query-open">FLT_PARAMETERS for IRP_MJ_NETWORK_QUERY_OPEN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-prepare-mdl-write">FLT_PARAMETERS for IRP_MJ_PREPARE_MDL_WRITE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-release-for-mod-write">FLT_PARAMETERS for IRP_MJ_RELEASE_FOR_MOD_WRITE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-volume-mount">FLT_PARAMETERS for IRP_MJ_VOLUME_MOUNT</a>


The following I/O operations do not have parameters:

<ul>
<li>IRP_MJ_ACQUIRE_FOR_CC_FLUSH</li>
<li>IRP_MJ_CLEANUP</li>
<li>IRP_MJ_CLOSE</li>
<li>IRP_MJ_FLUSH_BUFFERS</li>
<li>IRP_MJ_RELEASE_FOR_CC_FLUSH</li>
<li>IRP_MJ_RELEASE_FOR_SECTION_SYNCHRONIZATION</li>
<li>IRP_MJ_SHUTDOWN</li>
<li>IRP_MJ_VOLUME_DISMOUNT</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_io_parameter_block">FLT_IO_PARAMETER_BLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltsetcallbackdatadirty">FltSetCallbackDataDirty</a>
 

 


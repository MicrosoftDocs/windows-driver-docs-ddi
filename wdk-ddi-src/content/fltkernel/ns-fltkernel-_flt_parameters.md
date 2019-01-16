---
UID: NS:fltkernel._FLT_PARAMETERS
title: "_FLT_PARAMETERS"
description: The FLT_PARAMETERS union defines the request-type-specific parameters associated with an I/O operation.
old-location: ifsk\flt_parameters.htm
tech.root: ifsk
ms.assetid: 62aa20b7-ce5c-4d42-bce2-1d76a98887ed
ms.date: 04/16/2018
ms.keywords: "*PFLT_PARAMETERS, FLT_PARAMETERS, FLT_PARAMETERS union [Installable File System Drivers], FltSystemStructures_2ebb0ec7-76cc-49a3-b2ec-186f67369bbb.xml, PFLT_PARAMETERS, PFLT_PARAMETERS union pointer [Installable File System Drivers], _FLT_PARAMETERS, fltkernel/FLT_PARAMETERS, fltkernel/PFLT_PARAMETERS, ifsk.flt_parameters"
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	fltkernel.h
api_name:
-	FLT_PARAMETERS
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



This structure is stored in the <b>Parameters</b> field of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544638">FLT_IO_PARAMETER_BLOCK</a> structure for the operation. (A pointer to the FLT_IO_PARAMETER_BLOCK structure is stored in the <b>Iopb</b> field of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a> structure for the operation.) 

For the specific FLT_PARAMETERS union component used in each type of I/O operation, see the following reference entries. 


<a href="https://msdn.microsoft.com/library/windows/hardware/ff544687">FLT_PARAMETERS for IRP_MJ_CREATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544692">FLT_PARAMETERS for IRP_MJ_DEVICE_CONTROL and IRP_MJ_INTERNAL_DEVICE_CONTROL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544695">FLT_PARAMETERS for IRP_MJ_DIRECTORY_CONTROL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544705">FLT_PARAMETERS for IRP_MJ_FILE_SYSTEM_CONTROL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544709">FLT_PARAMETERS for IRP_MJ_LOCK_CONTROL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544742">FLT_PARAMETERS for IRP_MJ_PNP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544751">FLT_PARAMETERS for IRP_MJ_QUERY_EA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544756">FLT_PARAMETERS for IRP_MJ_QUERY_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544759">FLT_PARAMETERS for IRP_MJ_QUERY_QUOTA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544765">FLT_PARAMETERS for IRP_MJ_QUERY_SECURITY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544768">FLT_PARAMETERS for IRP_MJ_QUERY_VOLUME_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544770">FLT_PARAMETERS for IRP_MJ_READ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544781">FLT_PARAMETERS for IRP_MJ_SET_EA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544789">FLT_PARAMETERS for IRP_MJ_SET_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544792">FLT_PARAMETERS for IRP_MJ_SET_QUOTA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544794">FLT_PARAMETERS for IRP_MJ_SET_SECURITY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544798">FLT_PARAMETERS for IRP_MJ_SET_VOLUME_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544808">FLT_PARAMETERS for IRP_MJ_WRITE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544678">FLT_PARAMETERS for IRP_MJ_ACQUIRE_FOR_MOD_WRITE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544684">FLT_PARAMETERS for IRP_MJ_ACQUIRE_FOR_SECTION_SYNCHRONIZATION</a>

[FLT_PARAMETERS for IRP_MJ_QUERY_OPEN](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-query-open)

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544700">FLT_PARAMETERS for IRP_MJ_FAST_IO_CHECK_IF_POSSIBLE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544713">FLT_PARAMETERS for IRP_MJ_MDL_READ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544719">FLT_PARAMETERS for IRP_MJ_MDL_READ_COMPLETE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544725">FLT_PARAMETERS for IRP_MJ_MDL_WRITE_COMPLETE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544731">FLT_PARAMETERS for IRP_MJ_NETWORK_QUERY_OPEN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544749">FLT_PARAMETERS for IRP_MJ_PREPARE_MDL_WRITE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544774">FLT_PARAMETERS for IRP_MJ_RELEASE_FOR_MOD_WRITE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544804">FLT_PARAMETERS for IRP_MJ_VOLUME_MOUNT</a>


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544638">FLT_IO_PARAMETER_BLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544383">FltSetCallbackDataDirty</a>
 

 


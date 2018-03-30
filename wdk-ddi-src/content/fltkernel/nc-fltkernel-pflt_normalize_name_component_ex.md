---
UID: NC:fltkernel.PFLT_NORMALIZE_NAME_COMPONENT_EX
title: PFLT_NORMALIZE_NAME_COMPONENT_EX
author: windows-driver-content
description: A minifilter driver that provides file names for the filter manager's name cache can register a routine of type PFLT_NORMALIZE_NAME_COMPONENT_EX as the minifilter driver's NormalizeNameComponentExCallback callback routine.
old-location: ifsk\pflt_normalize_name_component_ex.htm
old-project: ifsk
ms.assetid: 7c2bc90a-c724-4787-b604-f7257a83aae7
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltCallbacks_d5ac42d8-4a17-49c0-b46f-f0c055ded4f3.xml, NormalizeNameComponentExCallback, NormalizeNameComponentExCallback routine [Installable File System Drivers], PFLT_NORMALIZE_NAME_COMPONENT_EX, fltkernel/NormalizeNameComponentExCallback, ifsk.pflt_normalize_name_component_ex
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: fltkernel.h
req.include-header: Fltkernel.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	fltkernel.h
api_name:
-	NormalizeNameComponentExCallback
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# PFLT_NORMALIZE_NAME_COMPONENT_EX callback


## -description


A minifilter driver that provides file names for the filter manager's name cache can register a routine of type PFLT_NORMALIZE_NAME_COMPONENT_EX as the minifilter driver's <i>NormalizeNameComponentExCallback</i> callback routine.


## -parameters




### -param Instance [in]

Opaque instance pointer for the minifilter driver instance that this callback routine is registered for.


### -param FileObject [in]

Pointer to the file object for the file whose name is being requested or the file that is the target of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549366">IRP_MJ_SET_INFORMATION</a> operation if the FLTFL_NORMALIZE_NAME_DESTINATION_FILE_NAME flag is set.  See the <i>Flags</i> parameter below for more information.


### -param ParentDirectory [in]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure that contains the name of the parent directory for this name component. 


### -param VolumeNameLength [in]

Length, in bytes, of the parent directory name that is stored in the structure that the <i>ParentDirectory</i> parameter points to. 


### -param Component [in]

Pointer to a UNICODE_STRING structure that contains the name component to be expanded. 


### -param ExpandComponentName [out]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540329">FILE_NAMES_INFORMATION</a> structure that receives the expanded (normalized) file name information for the name component. 


### -param ExpandComponentNameLength [in]

Length, in bytes, of the buffer that the <i>ExpandComponentName</i> parameter points to. 


### -param Flags [in]

Name normalization flags.  FLTFL_NORMALIZE_NAME_CASE_SENSITIVE specifies that the name to be normalized is case-sensitive.  FLTFL_NORMALIZE_NAME_DESTINATION_FILE_NAME specifies that the callback routine has been called to service an <a href="https://msdn.microsoft.com/library/windows/hardware/ff543003">FltGetDestinationFileNameInformation</a> routine call.  If the FLTFL_NORMALIZE_NAME_DESTINATION_FILE_NAME flag is set, <i>FileObject</i> represents the file/directory that is the target of the IRP_MJ_SET_INFORMATION operation. If the FLTFL_NORMALIZE_NAME_DESTINATION_FILE_NAME flag is not set, <i>FileObject</i> represents the file/directory whose name is being requested.


### -param *NormalizationContext [in, out]

Pointer to minifilter driver-provided context information to be passed in any subsequent calls to this callback routine that are made to normalize the remaining components in the same file name path. 


## -returns



This callback routine returns STATUS_SUCCESS or an appropriate NTSTATUS value. If the name component that the <i>Component</i> parameter specifies does not exist in the parent directory that the <i>ParentDirectory</i> parameter specifies, this callback routine should return STATUS_NO_SUCH_FILE. If this callback routine issues an IRP_MN_QUERY_DIRECTORY (FileNamesInformation) request to the parent directory, the file system returns the correct status code. In this situation, this callback can simply return the status code that the file system returns.




## -remarks



A minifilter driver that provides file names for the filter manager's name cache can register a routine of type PFLT_NORMALIZE_NAME_COMPONENT_EX as the minifilter driver's <i>NormalizeNameComponentExCallback</i> callback routine.  

The principal difference between the <i>NormalizeNameComponentExCallback</i> callback routine and the <i>NormalizeNameComponentCallback </i>callback routine (of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff551102">PFLT_NORMALIZE_NAME_COMPONENT</a>) is that the <i>NormalizeNameComponentExCallback</i> callback routine supports the additional <i>FileObject</i> parameter.  The file object (<i>FileObject</i>) can be used by the minifilter driver to retrieve the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556863">TXN_PARAMETER_BLOCK</a> structure for the operation that the file/directory is participating in by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548412">IoGetTransactionParameterBlock</a> routine. The TXN_PARAMETER_BLOCK structure can be used by the minifilter driver to issue its own create requests in the context of the transaction that this file object is participating in. 

To register this callback routine, the minifilter driver stores the address of a routine of type PFLT_NORMALIZE_NAME_COMPONENT_EX in the <b>NormalizeNameComponentExCallback</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544811">FLT_REGISTRATION</a> structure that the minifilter driver passes as a parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff544305">FltRegisterFilter</a>. 

The filter manager calls this callback routine to query the minifilter driver for the normalized names for components in the file name path whose names the minifilter driver has modified. If the file name path contains more than one such component, the filter manager can call this callback routine multiple times in the process of normalizing all the components in the path. The minifilter driver can use the <i>NormalizationContext</i> parameter to pass context information to subsequent calls to this callback routine. 

If the minifilter driver uses the <i>NormalizationContext</i> parameter, it should also register a normalization context cleanup callback routine. For more information, see the reference entry for <a href="https://msdn.microsoft.com/library/windows/hardware/ff551100">PFLT_NORMALIZE_CONTEXT_CLEANUP</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540329">FILE_NAMES_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544811">FLT_REGISTRATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543003">FltGetDestinationFileNameInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544305">FltRegisterFilter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549366">IRP_MJ_SET_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548412">IoGetTransactionParameterBlock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551087">PFLT_GENERATE_FILE_NAME</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551100">PFLT_NORMALIZE_CONTEXT_CLEANUP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551102">PFLT_NORMALIZE_NAME_COMPONENT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556863">TXN_PARAMETER_BLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
 

 


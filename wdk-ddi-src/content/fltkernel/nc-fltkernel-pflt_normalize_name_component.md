---
UID: NC:fltkernel.PFLT_NORMALIZE_NAME_COMPONENT
title: PFLT_NORMALIZE_NAME_COMPONENT
author: windows-driver-content
description: A minifilter driver that provides file names for the filter manager's name cache can register a routine of type PFLT_NORMALIZE_NAME_COMPONENT as the minifilter driver's NormalizeNameComponentCallback routine.
old-location: ifsk\pflt_normalize_name_component.htm
old-project: ifsk
ms.assetid: 7050e872-3976-4842-9d16-50caf415acbc
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltCallbacks_674b1fbb-234b-4505-931e-8148e2f23d1b.xml, NormalizeNameComponentCallback, NormalizeNameComponentCallback routine [Installable File System Drivers], PFLT_NORMALIZE_NAME_COMPONENT, fltkernel/NormalizeNameComponentCallback, ifsk.pflt_normalize_name_component
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
-	NormalizeNameComponentCallback
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# PFLT_NORMALIZE_NAME_COMPONENT callback


## -description


A minifilter driver that provides file names for the filter manager's name cache can register a routine of type PFLT_NORMALIZE_NAME_COMPONENT as the minifilter driver's <i>NormalizeNameComponentCallback</i> routine. 


## -prototype


````
PFLT_NORMALIZE_NAME_COMPONENT NormalizeNameComponentCallback;

NTSTATUS NormalizeNameComponentCallback(
  _In_    PFLT_INSTANCE            Instance,
  _In_    PCUNICODE_STRING         ParentDirectory,
  _In_    USHORT                   VolumeNameLength,
  _In_    PCUNICODE_STRING         Component,
  _Out_   PFILE_NAMES_INFORMATION  ExpandComponentName,
  _In_    ULONG                    ExpandComponentNameLength,
  _In_    FLT_NORMALIZE_NAME_FLAGS Flags,
  _Inout_ PVOID                    *NormalizationContext
)
{ ... }
````


## -parameters




### -param Instance [in]

Opaque instance pointer for the minifilter driver instance that this callback routine is registered for. 


### -param ParentDirectory [in]

Pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains the name of the parent directory for this name component. 


### -param VolumeNameLength [in]

Length, in bytes, of the parent directory name stored in the structure that the <i>ParentDirectory</i> parameter points to. 


### -param Component [in]

Pointer to a UNICODE_STRING structure that contains the name component to be expanded. 


### -param ExpandComponentName [out]

Pointer to a <a href="..\ntifs\ns-ntifs-_file_names_information.md">FILE_NAMES_INFORMATION</a> structure that receives the expanded (normalized) file name information for the name component. 


### -param ExpandComponentNameLength [in]

Length, in bytes, of the buffer that the <i>ExpandComponentName</i> parameter points to. 


### -param Flags [in]

Name normalization flags.  FLTFL_NORMALIZE_NAME_CASE_SENSITIVE specifies that the name to be normalized is case-sensitive.  FLTFL_NORMALIZE_NAME_DESTINATION_FILE_NAME specifies that the callback routine has been called to service a <a href="..\fltkernel\nf-fltkernel-fltgetdestinationfilenameinformation.md">FltGetDestinationFileNameInformation</a> routine call.


### -param *NormalizationContext [in, out]

Pointer to minifilter driver-provided context information to be passed in any subsequent calls to this callback routine that are made to normalize the remaining components in the same file name path. 


## -returns



This callback routine returns STATUS_SUCCESS or an appropriate NTSTATUS value. If the name component that the <i>Component</i> parameter specifies does not exist in the parent directory that the <i>ParentDirectory</i> parameter specifies, this callback routine should return STATUS_NO_SUCH_FILE. If this callback routine issues an IRP_MN_QUERY_DIRECTORY (FileNamesInformation) request to the parent directory, the file system returns the correct status code. In this situation, this callback can simply return the status code that the file system returns.




## -remarks



A minifilter driver that provides file names for the filter manager's name cache can register a routine of type PFLT_NORMALIZE_NAME_COMPONENT as the minifilter driver's <i>NormalizeNameComponentCallback</i> routine. 

To register this callback routine, the minifilter driver stores the address of a routine of type PFLT_NORMALIZE_NAME_COMPONENT in the <b>NormalizeNameComponentCallback</b> member of the <a href="..\fltkernel\ns-fltkernel-_flt_registration.md">FLT_REGISTRATION</a> structure that the minifilter driver passes as a parameter to <a href="..\fltkernel\nf-fltkernel-fltregisterfilter.md">FltRegisterFilter</a>. 

The filter manager calls this callback routine to query the minifilter driver for the normalized names for components in the file name path whose names the minifilter driver has modified. If the file name path contains more than one such component, the filter manager can call this callback routine multiple times in the process of normalizing all the components in the path. The minifilter driver can use the <i>NormalizationContext</i> parameter to pass context information to subsequent calls to this callback routine. 

If the minifilter driver uses the <i>NormalizationContext</i> parameter, it should also register a normalization context cleanup callback routine. For more information, see the reference entry for <a href="..\fltkernel\nc-fltkernel-pflt_normalize_context_cleanup.md">PFLT_NORMALIZE_CONTEXT_CLEANUP</a>. 




## -see-also

<a href="..\fltkernel\ns-fltkernel-_flt_registration.md">FLT_REGISTRATION</a>



<a href="..\ntifs\ns-ntifs-_file_names_information.md">FILE_NAMES_INFORMATION</a>



<a href="..\fltkernel\nc-fltkernel-pflt_generate_file_name.md">PFLT_GENERATE_FILE_NAME</a>



<a href="..\fltkernel\nf-fltkernel-fltregisterfilter.md">FltRegisterFilter</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\fltkernel\nc-fltkernel-pflt_normalize_name_component_ex.md">PFLT_NORMALIZE_NAME_COMPONENT_EX</a>



<a href="..\fltkernel\nc-fltkernel-pflt_normalize_context_cleanup.md">PFLT_NORMALIZE_CONTEXT_CLEANUP</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20PFLT_NORMALIZE_NAME_COMPONENT routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


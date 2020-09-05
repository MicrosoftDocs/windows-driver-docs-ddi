---
UID: NC:fltkernel.PFLT_GENERATE_FILE_NAME
title: PFLT_GENERATE_FILE_NAME (fltkernel.h)
description: A minifilter driver that provides file names for the filter manager's name cache can register a routine of type PFLT_GENERATE_FILE_NAME as the minifilter driver's GenerateFileNameCallback routine.
old-location: ifsk\pflt_generate_file_name.htm
tech.root: ifsk
ms.assetid: 04e7e4db-2cf6-4312-8964-2c69c96953a3
ms.date: 04/16/2018
keywords: ["PFLT_GENERATE_FILE_NAME callback function"]
ms.keywords: FltCallbacks_0075602c-1093-445c-a949-ea282cf736e7.xml, GenerateFileNameCallback, GenerateFileNameCallback routine [Installable File System Drivers], PFLT_GENERATE_FILE_NAME, fltkernel/GenerateFileNameCallback, ifsk.pflt_generate_file_name
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PFLT_GENERATE_FILE_NAME
 - fltkernel/PFLT_GENERATE_FILE_NAME
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - fltkernel.h
api_name:
 - GenerateFileNameCallback
---

# PFLT_GENERATE_FILE_NAME callback function


## -description

A minifilter driver that provides file names for the filter manager's name cache can register a routine of type <i>PFLT_GENERATE_FILE_NAME</i> as the minifilter driver's <i>GenerateFileNameCallback</i> routine.

## -parameters

### -param Instance 

[in]
Opaque instance pointer for the minifilter driver instance that this callback routine is registered for.

### -param FileObject 

[in]
A pointer to a file object for the file whose name is being requested.

### -param CallbackData 

[in, optional]
A pointer to the callback data structure for the operation during which this name is being requested. This parameter is <b>NULL</b> when <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetfilenameinformationunsafe">FltGetFileNameInformationUnsafe</a> is called to retrieve the name of the file.

### -param NameOptions 

[in]

<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-file-name-options">FLT_FILE_NAME_OPTIONS</a> value that specifies the name format, query method, and flags for this file name information query.

### -param CacheFileNameInformation 

[out]
A pointer to a Boolean value specifying whether this name can be cached. Set to <b>TRUE</b> on output if the name can be cached; set to <b>FALSE</b> otherwise.

### -param FileName 

[out]
A pointer to a filter manager-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_name_control">FLT_NAME_CONTROL</a> structure to receive the file name on output.

## -returns

This callback routine returns STATUS_SUCCESS or an appropriate NTSTATUS value.

## -remarks

A minifilter driver that provides file names for the filter manager's name cache can register a routine of type <i>PFLT_GENERATE_FILE_NAME</i> as the minifilter driver's <i>GenerateFileNameCallback</i> routine. 

To register this callback routine, the minifilter driver stores the address of a routine of type <i>PFLT_GENERATE_FILE_NAME</i> in the <i>GenerateFileNameCallback</i> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_registration">FLT_REGISTRATION</a> structure that the minifilter driver passes as a parameter to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltregisterfilter">FltRegisterFilter</a>. 

The filter manager calls this callback routine to allow the minifilter driver to intercept file name requests by other minifilter drivers above it in the minifilter driver instance stack. Using this callback routine and the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_normalize_name_component">PFLT_NORMALIZE_NAME_COMPONENT</a> callback routine, the minifilter driver can provide its own file name information. 

To determine which file name format is being requested, call <a href="https://docs.microsoft.com/previous-versions/ff543030(v=vs.85)">FltGetFileNameFormat</a> on the <i>NameOptions</i> parameter. 

Prior to Windows 8, this callback routine is called only for opened file names and short file names. When the filter manager receives a request for a normalized file name, it calls this callback routine to request the opened file name. Then it calls the minifilter driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_normalize_name_component">PFLT_NORMALIZE_NAME_COMPONENT</a> callback to normalize each component in the file name.


Starting with Windows 8, this callback routine is also called for normalized names.  When the filter manager receives a request for a normalized file name, it calls this callback routine with FLT_FILE_NAME_NORMALIZED specified in the <i>NameOptions</i> parameter.  If the minifilter returns STATUS_SUCCESS from this callback, the minifilter’s <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_normalize_name_component">PFLT_NORMALIZE_NAME_COMPONENT</a> callback will not be called.  If the minifilter returns a failure code (such as STATUS_NOT_SUPPORTED), the filter manager will call this callback routine again, requesting the opened file name.  The filter manager will then call the minifilter driver’s <i>PFLT_NORMALIZE_NAME_COMPONENT</i> callback to normalize each component in the file name.


When this callback routine is invoked, the minifilter driver generates its own file name information, based on the file system's file name information for the file. To get the file system's file name information for a file, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetfilenameinformation">FltGetFileNameInformation</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetfilenameinformationunsafe">FltGetFileNameInformationUnsafe</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetdestinationfilenameinformation">FltGetDestinationFileNameInformation</a>. 

For opened file names, the generated file name information should include volume information. For a remote file, it should include share information as well. 

The following is an example of an opened file name for a remote file: 


```
\Device\LanManRedirector\MyServer\MyShare\Docume~1\MyUser\My Documents\TestRe~1.txt:stream1
```

For more information about file name formats, see the reference entries for <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_file_name_information">FLT_FILE_NAME_INFORMATION</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltparsefilenameinformation">FltParseFileNameInformation</a>. 

After it generates the file name information, the minifilter driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcheckandgrownamecontrol">FltCheckAndGrowNameControl</a> to check whether the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_name_control">FLT_NAME_CONTROL</a> structure that the <i>FileName</i> parameter points to contains a name buffer that is large enough to hold the generated file name. If the name buffer is too small, <b>FltCheckAndGrowNameControl</b> replaces it with a larger one. The minifilter driver then stores the file name information into the name buffer and returns.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_file_name_information">FLT_FILE_NAME_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-file-name-options">FLT_FILE_NAME_OPTIONS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_name_control">FLT_NAME_CONTROL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_registration">FLT_REGISTRATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcheckandgrownamecontrol">FltCheckAndGrowNameControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetdestinationfilenameinformation">FltGetDestinationFileNameInformation</a>



<a href="https://docs.microsoft.com/previous-versions/ff543030(v=vs.85)">FltGetFileNameFormat</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetfilenameinformation">FltGetFileNameInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetfilenameinformationunsafe">FltGetFileNameInformationUnsafe</a>



<a href="https://docs.microsoft.com/previous-versions/ff543040(v=vs.85)">FltGetFileNameQueryMethod</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltparsefilename">FltParseFileName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltparsefilenameinformation">FltParseFileNameInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltpurgefilenameinformationcache">FltPurgeFileNameInformationCache</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltregisterfilter">FltRegisterFilter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_normalize_context_cleanup">PFLT_NORMALIZE_CONTEXT_CLEANUP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_normalize_name_component">PFLT_NORMALIZE_NAME_COMPONENT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_normalize_name_component_ex">PFLT_NORMALIZE_NAME_COMPONENT_EX</a>


---
UID: NF:fltkernel.FltPurgeFileNameInformationCache
title: FltPurgeFileNameInformationCache function
author: windows-driver-content
description: FltPurgeFileNameInformationCache purges from the Filter Manager's name cache all file name information structures that were generated from names provided by the given minifilter driver instance.
old-location: ifsk\fltpurgefilenameinformationcache.htm
old-project: ifsk
ms.assetid: d3c4d041-0589-46f5-a514-8efb0db642c7
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ifsk.fltpurgefilenameinformationcache, fltkernel/FltPurgeFileNameInformationCache, FltApiRef_p_to_z_2b9315b1-c1c1-4739-af0e-0acebae1c59e.xml, FltPurgeFileNameInformationCache, FltPurgeFileNameInformationCache function [Installable File System Drivers]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltPurgeFileNameInformationCache
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltPurgeFileNameInformationCache function


## -description


<b>FltPurgeFileNameInformationCache</b> purges from the Filter Manager's name cache all file name information structures that were generated from names provided by the given minifilter driver instance. 


## -syntax


````
NTSTATUS FltPurgeFileNameInformationCache(
  _In_     PFLT_INSTANCE Instance,
  _In_opt_ PFILE_OBJECT  FileObject
);
````


## -parameters




### -param Instance [in]

Opaque instance (PFLT_INSTANCE) pointer for the minifilter driver instance whose names are to be purged. This parameter is required and cannot be <b>NULL</b>. 


### -param FileObject [in, optional]

Optional pointer to a file object for which all names are to be purged. If this parameter is <b>NULL</b>, all names for the minifilter driver instance specified by the <i>Instance</i> parameter are purged. 


## -returns


<b>FltPurgeFileNameInformationCache</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value. 



## -remarks


A minifilter driver that provides file names for the Filter Manager's name cache can call <b>FltPurgeFileNameInformationCache</b> to purge the names provided for a given minifilter driver instance. This is most commonly done when a name-providing filter unloads. 

The file name information structures are not freed until all references are released. 



## -see-also

<a href="..\fltkernel\nc-fltkernel-pflt_normalize_name_component.md">PFLT_NORMALIZE_NAME_COMPONENT</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543030">FltGetFileNameFormat</a>

<a href="..\fltkernel\nc-fltkernel-pflt_normalize_context_cleanup.md">PFLT_NORMALIZE_CONTEXT_CLEANUP</a>

<a href="..\fltkernel\nc-fltkernel-pflt_generate_file_name.md">PFLT_GENERATE_FILE_NAME</a>

<a href="..\fltkernel\nf-fltkernel-fltcheckandgrownamecontrol.md">FltCheckAndGrowNameControl</a>

<a href="..\fltkernel\nf-fltkernel-fltgetfilenameinformation.md">FltGetFileNameInformation</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543040">FltGetFileNameQueryMethod</a>

<a href="..\fltkernel\nf-fltkernel-fltgetfilenameinformationunsafe.md">FltGetFileNameInformationUnsafe</a>

<a href="..\fltkernel\ns-fltkernel-_flt_name_control.md">FLT_NAME_CONTROL</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltPurgeFileNameInformationCache function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


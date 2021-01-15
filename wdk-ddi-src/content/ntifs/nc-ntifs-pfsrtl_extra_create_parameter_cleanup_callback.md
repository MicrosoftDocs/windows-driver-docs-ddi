---
UID: NC:ntifs.PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK
title: PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK (ntifs.h)
description: A filter driver can register a PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK-typed routine as the filter driver's CleanupCallback callback routine for an extra create parameter (ECP) context structure.
old-location: ifsk\pfsrtl_extra_create_parameter_cleanup_callback.htm
tech.root: ifsk
ms.date: 03/29/2018
keywords: ["PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK callback"]
ms.keywords: FilterCallbacks_afe97c84-8818-4577-ad94-8f8fdf044570.xml, PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK, PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK function pointer [Installable File System Drivers], ifsk.pfsrtl_extra_create_parameter_cleanup_callback, ntifs/PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of all Windows operating systems.
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
req.typenames: VOLUME_READ_PLEX_INPUT, *PVOLUME_READ_PLEX_INPUT
f1_keywords:
 - PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK
 - ntifs/PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ntifs.h
api_name:
 - PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK
---

# PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK callback

## -description

A filter driver can register a PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK-typed routine as the filter driver's *CleanupCallback* callback routine for an extra create parameter (ECP) context structure.

## -parameters

### -param EcpContext

[in, out] An ECP context pointer that was returned by the routine that allocated the ECP context structure.

### -param EcpType

[in[] A pointer to a GUID that was passed to the routine that allocated the ECP context structure, that indicates the extra create parameter type.  For more information, see [Using GUIDs in Drivers](/windows-hardware/drivers/kernel/using-guids-in-drivers).

## -remarks

When a filter driver allocates an ECP context structure, it can optionally specify a PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK-typed routine as the filter driver's *CleanupCallback* callback routine.  If the filter driver specifies a *CleanupCallback* callback routine, the operating system will invoke the *CleanupCallback* routine (regardless of IRQ level).  This *CleanupCallback* routine performs any necessary ECP context-related cleanup processing when the ECP context structure is deleted.

To specify a callback routine, a filter driver passes a pointer to the callback routine by using the *CleanupCallback* parameter of the routine that originally allocated the ECP context structure.  If a callback routine is not needed, a **NULL** value must be passed to the *CleanupCallback* parameter.

The following routines support the PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK-typed callback routine:

* [**FltAllocateExtraCreateParameter**](../fltkernel/nf-fltkernel-fltallocateextracreateparameter.md)
* [**FltAllocateExtraCreateParameterFromLookasideList**](../fltkernel/nf-fltkernel-fltallocateextracreateparameterfromlookasidelist.md)
* [**FsRtlAllocateExtraCreateParameter**](nf-ntifs-fsrtlallocateextracreateparameter.md)

## -see-also

[**ECP_LIST**](/previous-versions/windows/hardware/drivers/ff540148(v=vs.85))

[**FltAllocateExtraCreateParameter**](../fltkernel/nf-fltkernel-fltallocateextracreateparameter.md)

[**FltAllocateExtraCreateParameterFromLookasideList**](../fltkernel/nf-fltkernel-fltallocateextracreateparameterfromlookasidelist.md)

[**FltAllocateExtraCreateParameterList**](../fltkernel/nf-fltkernel-fltallocateextracreateparameterlist.md)

[**FltFreeExtraCreateParameter**](../fltkernel/nf-fltkernel-fltfreeextracreateparameter.md)

[**FltFreeExtraCreateParameterList**](../fltkernel/nf-fltkernel-fltfreeextracreateparameterlist.md)

[**FltRemoveExtraCreateParameter**](../fltkernel/nf-fltkernel-fltremoveextracreateparameter.md)

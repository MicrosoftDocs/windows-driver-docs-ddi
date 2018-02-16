---
UID: NF:fltkernel.FltFreeExtraCreateParameter
title: FltFreeExtraCreateParameter function
author: windows-driver-content
description: The FltFreeExtraCreateParameter routine frees the memory for an ECP context structure.
old-location: ifsk\fltfreeextracreateparameter.htm
old-project: ifsk
ms.assetid: 2fc0dc67-ac82-4892-8321-632fe26e1616
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: FltFreeExtraCreateParameter routine [Installable File System Drivers], FltFreeExtraCreateParameter, FltApiRef_e_to_o_d5948c86-8750-4684-9f66-0f0b34949714.xml, ifsk.fltfreeextracreateparameter, fltkernel/FltFreeExtraCreateParameter
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available starting with Windows Vista.
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
req.dll: FltMgr.sys
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	FltMgr.sys
apiname:
-	FltFreeExtraCreateParameter
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltFreeExtraCreateParameter function


## -description


The <b>FltFreeExtraCreateParameter</b> routine frees the memory for an ECP context structure.


## -syntax


````
VOID FltFreeExtraCreateParameter(
  _In_ PFLT_FILTER Filter,
  _In_ PVOID       EcpContext
);
````


## -parameters




### -param Filter [in]

Opaque filter pointer for the minifilter driver. This pointer uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded.


### -param EcpContext [in]

Pointer to the extra create parameter (ECP) context structure to be freed.


## -returns



None.




## -remarks



If the ECP context structure to be freed is still attached to an ECP list, it must first be detached from the list by the <a href="..\fltkernel\nf-fltkernel-fltremoveextracreateparameter.md">FltRemoveExtraCreateParameter</a> routine before the <b>FltFreeExtraCreateParameter</b> routine can be called to free it.

If a cleanup callback routine of type PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK was defined for the given ECP context structure, this callback routine is invoked upon deletion of the ECP context structure.  For more information, see <a href="..\ntifs\nc-ntifs-pfsrtl_extra_create_parameter_cleanup_callback.md">PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK</a>. 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltsetecplistintocallbackdata.md">FltSetEcpListIntoCallbackData</a>



<a href="..\fltkernel\nf-fltkernel-fltfreeextracreateparameterlist.md">FltFreeExtraCreateParameterList</a>



<a href="..\fltkernel\nf-fltkernel-fltcreatefileex2.md">FltCreateFileEx2</a>



<a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a>



<a href="..\fltkernel\nf-fltkernel-fltinsertextracreateparameter.md">FltInsertExtraCreateParameter</a>



<a href="..\fltkernel\nf-fltkernel-fltremoveextracreateparameter.md">FltRemoveExtraCreateParameter</a>



<a href="..\ntifs\nc-ntifs-pfsrtl_extra_create_parameter_cleanup_callback.md">PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK</a>



<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameter.md">FltAllocateExtraCreateParameter</a>



<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameterfromlookasidelist.md">FltAllocateExtraCreateParameterFromLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>



<a href="..\fltkernel\nf-fltkernel-fltgetecplistfromcallbackdata.md">FltGetEcpListFromCallbackData</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltFreeExtraCreateParameter routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


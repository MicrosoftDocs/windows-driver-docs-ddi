---
UID: NF:fltkernel.FltFreeExtraCreateParameter
title: FltFreeExtraCreateParameter function
author: windows-driver-content
description: The FltFreeExtraCreateParameter routine frees the memory for an ECP context structure.
old-location: ifsk\fltfreeextracreateparameter.htm
old-project: ifsk
ms.assetid: 2fc0dc67-ac82-4892-8321-632fe26e1616
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FltApiRef_e_to_o_d5948c86-8750-4684-9f66-0f0b34949714.xml, FltFreeExtraCreateParameter, FltFreeExtraCreateParameter routine [Installable File System Drivers], fltkernel/FltFreeExtraCreateParameter, ifsk.fltfreeextracreateparameter
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	FltMgr.sys
api_name:
-	FltFreeExtraCreateParameter
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltFreeExtraCreateParameter function


## -description


The <b>FltFreeExtraCreateParameter</b> routine frees the memory for an ECP context structure.


## -parameters




### -param Filter [in]

Opaque filter pointer for the minifilter driver. This pointer uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded.


### -param EcpContext [in]

Pointer to the extra create parameter (ECP) context structure to be freed.


## -returns



None.




## -remarks



If the ECP context structure to be freed is still attached to an ECP list, it must first be detached from the list by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544339">FltRemoveExtraCreateParameter</a> routine before the <b>FltFreeExtraCreateParameter</b> routine can be called to free it.

If a cleanup callback routine of type PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK was defined for the given ECP context structure, this callback routine is invoked upon deletion of the ECP context structure.  For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff551124">PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541728">FltAllocateExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541734">FltAllocateExtraCreateParameterFromLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541939">FltCreateFileEx2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542964">FltFreeExtraCreateParameterList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543016">FltGetEcpListFromCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543305">FltInsertExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544339">FltRemoveExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544510">FltSetEcpListIntoCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548283">IoCreateFileEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551124">PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK</a>
 

 


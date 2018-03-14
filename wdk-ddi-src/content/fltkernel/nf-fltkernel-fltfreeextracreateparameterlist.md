---
UID: NF:fltkernel.FltFreeExtraCreateParameterList
title: FltFreeExtraCreateParameterList function
author: windows-driver-content
description: The FltFreeExtraCreateParameterList routine frees an extra create parameter (ECP) list structure.
old-location: ifsk\fltfreeextracreateparameterlist.htm
old-project: ifsk
ms.assetid: d8732904-273d-4595-ac90-1b731676620a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_e_to_o_a0e2c974-153f-4566-996c-5e291229cbf0.xml, FltFreeExtraCreateParameterList, FltFreeExtraCreateParameterList routine [Installable File System Drivers], fltkernel/FltFreeExtraCreateParameterList, ifsk.fltfreeextracreateparameterlist
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
req.dll: 
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	FltMgr.lib
-	FltMgr.dll
api_name:
-	FltFreeExtraCreateParameterList
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltFreeExtraCreateParameterList function


## -description


The <b>FltFreeExtraCreateParameterList</b> routine frees an extra create parameter (ECP) list structure.


## -syntax


````
VOID FltFreeExtraCreateParameterList(
  _In_ PFLT_FILTER Filter,
  _In_ PECP_LIST   EcpList
);
````


## -parameters




### -param Filter [in]

Opaque filter pointer for the minifilter driver. This pointer uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded.


### -param EcpList [in]

Pointer to the ECP list structure to be freed.


## -returns



None.




## -remarks



<b>FltFreeExtraCreateParameterList</b> frees an ECP list structure including any list elements, if they exist.  




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameterfromlookasidelist.md">FltAllocateExtraCreateParameterFromLookasideList</a>



<a href="..\fltkernel\nf-fltkernel-fltremoveextracreateparameter.md">FltRemoveExtraCreateParameter</a>



<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameterlist.md">FltAllocateExtraCreateParameterList</a>



<a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a>



<a href="..\fltkernel\nf-fltkernel-fltinsertextracreateparameter.md">FltInsertExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>



<a href="..\fltkernel\nf-fltkernel-fltgetecplistfromcallbackdata.md">FltGetEcpListFromCallbackData</a>



<a href="..\fltkernel\nf-fltkernel-fltcreatefileex2.md">FltCreateFileEx2</a>



<a href="..\fltkernel\nf-fltkernel-fltfreeextracreateparameter.md">FltFreeExtraCreateParameter</a>



<a href="..\fltkernel\nf-fltkernel-fltsetecplistintocallbackdata.md">FltSetEcpListIntoCallbackData</a>



 

 



---
UID: NF:fltkernel.FltFreeExtraCreateParameterList
title: FltFreeExtraCreateParameterList function (fltkernel.h)
description: The FltFreeExtraCreateParameterList routine frees an extra create parameter (ECP) list structure.
old-location: ifsk\fltfreeextracreateparameterlist.htm
tech.root: ifsk
ms.assetid: d8732904-273d-4595-ac90-1b731676620a
ms.date: 04/16/2018
keywords: ["FltFreeExtraCreateParameterList function"]
ms.keywords: FltApiRef_e_to_o_a0e2c974-153f-4566-996c-5e291229cbf0.xml, FltFreeExtraCreateParameterList, FltFreeExtraCreateParameterList routine [Installable File System Drivers], fltkernel/FltFreeExtraCreateParameterList, ifsk.fltfreeextracreateparameterlist
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltFreeExtraCreateParameterList
 - fltkernel/FltFreeExtraCreateParameterList
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - FltMgr.lib
 - FltMgr.dll
api_name:
 - FltFreeExtraCreateParameterList
---

# FltFreeExtraCreateParameterList function


## -description

The <b>FltFreeExtraCreateParameterList</b> routine frees an extra create parameter (ECP) list structure.

## -parameters

### -param Filter 

[in]
Opaque filter pointer for the minifilter driver. This pointer uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded.

### -param EcpList 

[in]
Pointer to the ECP list structure to be freed.

## -returns

None.

## -remarks

<b>FltFreeExtraCreateParameterList</b> frees an ECP list structure including any list elements, if they exist.

## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff540148(v=vs.85)">ECP_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocateextracreateparameterfromlookasidelist">FltAllocateExtraCreateParameterFromLookasideList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocateextracreateparameterlist">FltAllocateExtraCreateParameterList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatefileex2">FltCreateFileEx2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfreeextracreateparameter">FltFreeExtraCreateParameter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetecplistfromcallbackdata">FltGetEcpListFromCallbackData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltinsertextracreateparameter">FltInsertExtraCreateParameter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltremoveextracreateparameter">FltRemoveExtraCreateParameter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetecplistintocallbackdata">FltSetEcpListIntoCallbackData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iocreatefileex">IoCreateFileEx</a>


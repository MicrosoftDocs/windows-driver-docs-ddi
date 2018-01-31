---
UID: NF:aux_klib.AuxKlibGetBugCheckData
title: AuxKlibGetBugCheckData function
author: windows-driver-content
description: The AuxKlibGetBugCheckData routine retrieves information about a bug check that has just occurred.
old-location: kernel\auxklibgetbugcheckdata.htm
old-project: kernel
ms.assetid: d41d0eba-14e3-48ff-874d-e52589cf716c
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.auxklibgetbugcheckdata, AuxKlibGetBugCheckData routine [Kernel-Mode Driver Architecture], aux_klib_3cb977df-feb6-4b52-afa1-b5e3038fc287.xml, aux_klib/AuxKlibGetBugCheckData, AuxKlibGetBugCheckData
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: aux_klib.h
req.include-header: Aux_klib.h
req.target-type: Universal
req.target-min-winverclnt: Supported starting with Windows 2000.
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
req.lib: Aux_Klib.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Aux_Klib.lib
-	Aux_Klib.dll
apiname:
-	AuxKlibGetBugCheckData
product: Windows
targetos: Windows
req.typenames: REPORT_ZONES_EXT_DATA, *PREPORT_ZONES_EXT_DATA
---

# AuxKlibGetBugCheckData function


## -description


The <b>AuxKlibGetBugCheckData</b> routine retrieves information about a bug check that has just occurred.


## -syntax


````
NTSTATUS AuxKlibGetBugCheckData(
  _Out_ PKBUGCHECK_DATA BugCheckData
);
````


## -parameters




#### - BugCheckData [out]

A pointer to a <a href="..\aux_klib\ns-aux_klib-_kbugcheck_data.md">KBUGCHECK_DATA</a> structure that contains information about the bug check. The <i>BugCheckData</i> size of this structure should be set equal to the size, in bytes, of the <b>KBUGCHECK_DATA</b> structure.


## -returns


<b>AuxKlibGetBugCheckData</b> returns STATUS_SUCCESS if the operation succeeds. The routine returns STATUS_INFO_LENGTH_MISMATCH if the <b>KBUGCHECK_DATA</b> structure's size is incorrect.



## -remarks


The <b>AuxKlibGetBugCheckData</b> routine can be called only from a <a href="..\wdm\nc-wdm-kbugcheck_callback_routine.md">BugCheckCallback</a> routine.

Drivers must call <a href="..\aux_klib\nf-aux_klib-auxklibinitialize.md">AuxKlibInitialize</a> before calling <b>AuxKlibGetBugCheckData</b>.



## -see-also

<a href="..\wdm\nc-wdm-kbugcheck_callback_routine.md">BugCheckCallback</a>

<a href="..\aux_klib\nf-aux_klib-auxklibinitialize.md">AuxKlibInitialize</a>

<a href="..\aux_klib\ns-aux_klib-_kbugcheck_data.md">KBUGCHECK_DATA</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20AuxKlibGetBugCheckData routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


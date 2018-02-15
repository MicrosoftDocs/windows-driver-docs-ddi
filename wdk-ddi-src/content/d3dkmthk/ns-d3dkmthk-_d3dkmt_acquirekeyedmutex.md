---
UID: NS:d3dkmthk._D3DKMT_ACQUIREKEYEDMUTEX
title: "_D3DKMT_ACQUIREKEYEDMUTEX"
author: windows-driver-content
description: The D3DKMT_ACQUIREKEYEDMUTEX structure describes a keyed mutex that the D3DKMTAcquireKeyedMutex function acquires.
old-location: display\d3dkmt_acquirekeyedmutex.htm
old-project: display
ms.assetid: de089f63-b2f4-4e8e-b653-15db3259a45e
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMT_ACQUIREKEYEDMUTEX structure [Display Devices], OpenGL_Structs_114ed313-61ac-4c09-97fa-8b47a0aa40d1.xml, D3DKMT_ACQUIREKEYEDMUTEX, d3dkmthk/D3DKMT_ACQUIREKEYEDMUTEX, display.d3dkmt_acquirekeyedmutex, _D3DKMT_ACQUIREKEYEDMUTEX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_ACQUIREKEYEDMUTEX is supported beginning with the Windows 7 operating system.
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmthk.h
apiname:
-	D3DKMT_ACQUIREKEYEDMUTEX
product: Windows
targetos: Windows
req.typenames: D3DKMT_ACQUIREKEYEDMUTEX
---

# _D3DKMT_ACQUIREKEYEDMUTEX structure


## -description


The D3DKMT_ACQUIREKEYEDMUTEX structure describes a keyed mutex that the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtacquirekeyedmutex.md">D3DKMTAcquireKeyedMutex</a> function acquires. 


## -syntax


````
typedef struct _D3DKMT_ACQUIREKEYEDMUTEX {
  D3DKMT_HANDLE  hKeyedMutex;
  UINT64         Key;
  PLARGE_INTEGER pTimeout;
  UINT64         FenceValue;
} D3DKMT_ACQUIREKEYEDMUTEX;
````


## -struct-fields




### -field hKeyedMutex

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the keyed mutex object to acquire. 


### -field Key

[in] A 64-bit value that specifies the key value to acquire the mutex for. 


### -field pTimeout

[in] A pointer to a time-out value that specifies the absolute or relative time, in 100-nanosecond units, at which acquiring the mutex is to be completed. 

A positive value specifies an absolute time, relative to January 1, 1601. A negative value specifies an interval relative to the current time. Absolute expiration times track any changes in the system time; relative expiration times are not affected by system time changes. 

If *<b>pTimeout</b> = 0, <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtacquirekeyedmutex.md">D3DKMTAcquireKeyedMutex</a> returns without waiting. If the caller supplies a <b>NULL</b> pointer, <b>D3DKMTAcquireKeyedMutex</b> waits indefinitely until the mutex object is set to the signaled state. 


### -field FenceValue

[out] A 64-bit value that specifies the current fence value of the GPU synchronization object. 


## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtacquirekeyedmutex.md">D3DKMTAcquireKeyedMutex</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_ACQUIREKEYEDMUTEX structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


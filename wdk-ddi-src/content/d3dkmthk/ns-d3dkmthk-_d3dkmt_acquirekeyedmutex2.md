---
UID: NS:d3dkmthk._D3DKMT_ACQUIREKEYEDMUTEX2
title: "_D3DKMT_ACQUIREKEYEDMUTEX2"
author: windows-driver-content
description: Describes a keyed mutex object that the D3DKMTAcquireKeyedMutex2 function acquires that includes private data.
old-location: display\d3dkmt_acquirekeyedmutex2.htm
old-project: display
ms.assetid: 6e7ccf24-6403-44bf-9369-d2825646e950
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMT_ACQUIREKEYEDMUTEX2 structure [Display Devices], d3dkmthk/D3DKMT_ACQUIREKEYEDMUTEX2, D3DKMT_ACQUIREKEYEDMUTEX2, display.d3dkmt_acquirekeyedmutex2, _D3DKMT_ACQUIREKEYEDMUTEX2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3dkmthk.h
apiname:
-	D3DKMT_ACQUIREKEYEDMUTEX2
product: Windows
targetos: Windows
req.typenames: D3DKMT_ACQUIREKEYEDMUTEX2
---

# _D3DKMT_ACQUIREKEYEDMUTEX2 structure


## -description


Describes a keyed mutex object that the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtacquirekeyedmutex2.md">D3DKMTAcquireKeyedMutex2</a> function acquires that includes private data.


## -syntax


````
typedef struct _D3DKMT_ACQUIREKEYEDMUTEX2 {
  D3DKMT_HANDLE  hKeyedMutex;
  UINT64         Key;
  PLARGE_INTEGER pTimeout;
  UINT64         FenceValue;
  VOID           *pPrivateRuntimeData;
  UINT           PrivateRuntimeDataSize;
} D3DKMT_ACQUIREKEYEDMUTEX2;
````


## -struct-fields




### -field hKeyedMutex

[in] A D3DKMT_HANDLE data type that represents a handle to the keyed mutex.


### -field Key

[in] The key value to acquire.


### -field pTimeout

[in] An NT-style timeout value.


### -field FenceValue

[out] The current fence value of the GPU sync object.


### -field pPrivateRuntimeData

[out] A pointer to a buffer to copy private data to.


### -field PrivateRuntimeDataSize

[in] The size, in bytes, of the <b>pPrivateRuntimeData</b> member.


## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtacquirekeyedmutex2.md">D3DKMTAcquireKeyedMutex2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_ACQUIREKEYEDMUTEX2 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


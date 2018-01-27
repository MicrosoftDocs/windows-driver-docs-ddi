---
UID: NS:d3dkmthk._D3DKMT_RELEASEKEYEDMUTEX2
title: _D3DKMT_RELEASEKEYEDMUTEX2
author: windows-driver-content
description: Describes a keyed mutex object that the D3DKMTReleaseKeyedMutex2 function releases that includes private data.
old-location: display\d3dkmt_releasekeyedmutex2.htm
old-project: display
ms.assetid: e343b11c-7cd1-4aea-a87c-e33577456851
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMT_RELEASEKEYEDMUTEX2, display.d3dkmt_releasekeyedmutex2, D3DKMT_RELEASEKEYEDMUTEX2 structure [Display Devices], d3dkmthk/D3DKMT_RELEASEKEYEDMUTEX2, _D3DKMT_RELEASEKEYEDMUTEX2
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
-	D3DKMT_RELEASEKEYEDMUTEX2
product: Windows
targetos: Windows
req.typenames: D3DKMT_RELEASEKEYEDMUTEX2
---

# _D3DKMT_RELEASEKEYEDMUTEX2 structure


## -description


Describes a keyed mutex object that the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtreleasekeyedmutex2.md">D3DKMTReleaseKeyedMutex2</a> function releases that includes private data.


## -syntax


````
typedef struct _D3DKMT_RELEASEKEYEDMUTEX2 {
  D3DKMT_HANDLE hKeyedMutex;
  UINT64        Key;
  UINT64        FenceValue;
  VOID          *pPrivateRuntimeData;
  UINT          PrivateRuntimeDataSize;
} D3DKMT_RELEASEKEYEDMUTEX2;
````


## -struct-fields




### -field hKeyedMutex

[in] A value of type <b>D3DKMT_HANDLE</b> that represents a kernel-mode handle to the keyed mutex object to release.


### -field Key

[in] A 64-bit value that specifies the key value to release the mutex to.


### -field FenceValue

[in] A 64-bit value that specifies the current fence value of the GPU synchronization object.


### -field pPrivateRuntimeData

[in] A pointer to a caller-supplied buffer where the runtime private data associated with the resource is stored.


### -field PrivateRuntimeDataSize

[in] The size, in bytes, of the buffer pointed to by the <b>pPrivateRuntimeData</b> member.


## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtreleasekeyedmutex2.md">D3DKMTReleaseKeyedMutex2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_RELEASEKEYEDMUTEX2 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


---
UID: NS:d3dkmthk._D3DKMT_CREATEKEYEDMUTEX2
title: "_D3DKMT_CREATEKEYEDMUTEX2"
author: windows-driver-content
description: Describes a keyed mutex that the D3DKMTCreateKeyedMutex2 function creates that includes private data.
old-location: display\d3dkmt_createkeyedmutex2.htm
old-project: display
ms.assetid: 6c4c07ff-5e37-4094-9dc3-57082dec8edf
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMT_CREATEKEYEDMUTEX2 structure [Display Devices], d3dkmthk/D3DKMT_CREATEKEYEDMUTEX2, _D3DKMT_CREATEKEYEDMUTEX2, D3DKMT_CREATEKEYEDMUTEX2, display.d3dkmt_createkeyedmutex2
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
-	D3DKMT_CREATEKEYEDMUTEX2
product: Windows
targetos: Windows
req.typenames: D3DKMT_CREATEKEYEDMUTEX2
---

# _D3DKMT_CREATEKEYEDMUTEX2 structure


## -description


Describes a keyed mutex that the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreatekeyedmutex2.md">D3DKMTCreateKeyedMutex2</a> function creates that includes private data.


## -syntax


````
typedef struct _D3DKMT_CREATEKEYEDMUTEX2 {
  UINT64                         InitialValue;
  D3DKMT_HANDLE                  hSharedHandle;
  D3DKMT_HANDLE                  hKeyedMutex;
  VOID                           *pPrivateRuntimeData;
  UINT                           PrivateRuntimeDataSize;
  D3DKMT_CREATEKEYEDMUTEX2_FLAGS Flags;
} D3DKMT_CREATEKEYEDMUTEX2;
````


## -struct-fields




#### - InitialValue

[in] A 64-bit value that specifies the initial value to create the keyed mutex for.


#### - hSharedHandle

[out] A value of type <b>D3DKMT_HANDLE</b> that represents a kernel-mode shared global handle to the keyed mutex object.


#### - hKeyedMutex

[out] A value of type <b>D3DKMT_HANDLE</b> that represents a kernel-mode handle to the keyed mutex object in the current process.


#### - pPrivateRuntimeData

[in] A pointer to a caller-supplied buffer where the runtime private data associated with the resource is stored.


#### - PrivateRuntimeDataSize

[in] The size, in bytes, of the buffer pointed to by the <b>pPrivateRuntimeData</b> member.


#### - Flags

[in] A <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_createkeyedmutex2_flags.md">D3DKMT_CREATEKEYEDMUTEX2_FLAGS</a> structure that indicates how to specify a handle to a keyed mutex object.


## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_createkeyedmutex2_flags.md">D3DKMT_CREATEKEYEDMUTEX2_FLAGS</a>

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreatekeyedmutex2.md">D3DKMTCreateKeyedMutex2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_CREATEKEYEDMUTEX2 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


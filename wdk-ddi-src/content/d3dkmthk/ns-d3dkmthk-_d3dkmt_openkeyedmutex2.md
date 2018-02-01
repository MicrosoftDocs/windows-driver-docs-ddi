---
UID: NS:d3dkmthk._D3DKMT_OPENKEYEDMUTEX2
title: "_D3DKMT_OPENKEYEDMUTEX2"
author: windows-driver-content
description: Describes a keyed mutex that the D3DKMTOpenKeyedMutex2 function opens.
old-location: display\d3dkmt_openkeyedmutex2.htm
old-project: display
ms.assetid: 7d746cac-42fd-4fb3-9384-ea690c2235f8
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMT_OPENKEYEDMUTEX2, _D3DKMT_OPENKEYEDMUTEX2, D3DKMT_OPENKEYEDMUTEX2 structure [Display Devices], d3dkmthk/D3DKMT_OPENKEYEDMUTEX2, display.d3dkmt_openkeyedmutex2
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
-	D3DKMT_OPENKEYEDMUTEX2
product: Windows
targetos: Windows
req.typenames: D3DKMT_OPENKEYEDMUTEX2
---

# _D3DKMT_OPENKEYEDMUTEX2 structure


## -description


Describes a keyed mutex that the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtopenkeyedmutex2.md">D3DKMTOpenKeyedMutex2</a> function opens.


## -syntax


````
typedef struct _D3DKMT_OPENKEYEDMUTEX2 {
  D3DKMT_HANDLE hSharedHandle;
  D3DKMT_HANDLE hKeyedMutex;
  VOID          *pPrivateRuntimeData;
  UINT          PrivateRuntimeDataSize;
} D3DKMT_OPENKEYEDMUTEX2;
````


## -struct-fields




### -field hSharedHandle

[in] A D3DKMT_HANDLE data type that represents a global handle to a keyed mutex.


### -field hKeyedMutex

[out] A D3DKMT_HANDLE data type that represents a handle to the keyed mutex in this process.


### -field pPrivateRuntimeData

[in] A buffer that contains initial private data. This buffer is copied only if the keyed mutex does not already have private data.


### -field PrivateRuntimeDataSize

[in] The size, in bytes, of the <b>pPrivateRuntimeData</b> member.


## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtopenkeyedmutex2.md">D3DKMTOpenKeyedMutex2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_OPENKEYEDMUTEX2 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


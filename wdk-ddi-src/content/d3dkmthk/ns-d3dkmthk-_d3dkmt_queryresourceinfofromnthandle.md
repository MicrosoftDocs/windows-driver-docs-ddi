---
UID: NS:d3dkmthk._D3DKMT_QUERYRESOURCEINFOFROMNTHANDLE
title: "_D3DKMT_QUERYRESOURCEINFOFROMNTHANDLE"
author: windows-driver-content
description: Describes information that is required to map a global NT handle to resource information.
old-location: display\d3dkmt_queryresourceinfofromnthandle.htm
old-project: display
ms.assetid: 098fe3b9-1169-4ff6-8822-0eb277cb73f9
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMT_QUERYRESOURCEINFOFROMNTHANDLE, display.d3dkmt_queryresourceinfofromnthandle, d3dkmthk/D3DKMT_QUERYRESOURCEINFOFROMNTHANDLE, _D3DKMT_QUERYRESOURCEINFOFROMNTHANDLE, D3DKMT_QUERYRESOURCEINFOFROMNTHANDLE structure [Display Devices]
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
-	D3DKMT_QUERYRESOURCEINFOFROMNTHANDLE
product: Windows
targetos: Windows
req.typenames: D3DKMT_QUERYRESOURCEINFOFROMNTHANDLE
---

# _D3DKMT_QUERYRESOURCEINFOFROMNTHANDLE structure


## -description


Describes information that is required to map a global NT handle to resource information.


## -syntax


````
typedef struct _D3DKMT_QUERYRESOURCEINFOFROMNTHANDLE {
  D3DKMT_HANDLE hDevice;
  HANDLE        hNtHandle;
  VOID          *pPrivateRuntimeData;
  UINT          PrivateRuntimeDataSize;
  UINT          TotalPrivateDriverDataSize;
  UINT          ResourcePrivateDriverDataSize;
  UINT          NumAllocations;
} D3DKMT_QUERYRESOURCEINFOFROMNTHANDLE;
````


## -struct-fields




### -field hDevice

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the device.


### -field hNtHandle

[in] A global NT handle to the resource that is to be queried.


### -field pPrivateRuntimeData

[in] A pointer to a caller-supplied buffer where the runtime private data associated with the resource will be copied to.


### -field PrivateRuntimeDataSize

[in] The size, in bytes, of the buffer pointed to by the <b>pPrivateRuntimeData</b> member.

[out] If <b>pPrivateRuntimeData</b> is <b>NULL</b>, this member is the size, in bytes, of the buffer required to receive the runtime private data. Otherwise, this member is the size, in bytes, of runtime private data copied into the buffer.


### -field TotalPrivateDriverDataSize

[out] The size, in bytes, of the buffer that is required to hold all the driver private data for all allocations associated with the resource.


### -field ResourcePrivateDriverDataSize

[out] The size, in bytes, of the driver's resource private data.


### -field NumAllocations

[out] The number of allocations associated with the resource.


## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtqueryresourceinfofromnthandle.md">D3DKMTQueryResourceInfoFromNtHandle</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_QUERYRESOURCEINFOFROMNTHANDLE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


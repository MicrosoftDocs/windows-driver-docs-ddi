---
UID: NS:d3dkmthk._D3DKMT_CREATEKEYEDMUTEX2_FLAGS
title: "_D3DKMT_CREATEKEYEDMUTEX2_FLAGS"
author: windows-driver-content
description: Indicates how a handle to a keyed mutex is specified.
old-location: display\d3dkmt_createkeyedmutex2_flags.htm
old-project: display
ms.assetid: 21c2d262-bf8c-48a3-9801-5c2bd73f0282
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "_D3DKMT_CREATEKEYEDMUTEX2_FLAGS, D3DKMT_CREATEKEYEDMUTEX2_FLAGS structure [Display Devices], D3DKMT_CREATEKEYEDMUTEX2_FLAGS, d3dkmthk/D3DKMT_CREATEKEYEDMUTEX2_FLAGS, display.d3dkmt_createkeyedmutex2_flags"
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
-	D3DKMT_CREATEKEYEDMUTEX2_FLAGS
product: Windows
targetos: Windows
req.typenames: D3DKMT_CREATEKEYEDMUTEX2_FLAGS
---

# _D3DKMT_CREATEKEYEDMUTEX2_FLAGS structure


## -description


Indicates how a handle to a keyed mutex is specified.


## -syntax


````
typedef struct _D3DKMT_CREATEKEYEDMUTEX2_FLAGS {
  union {
    struct {
      UINT NtSecuritySharing  :1;
      UINT Reserved  :31;
    };
    UINT   Value;
  };
} D3DKMT_CREATEKEYEDMUTEX2_FLAGS;
````


## -struct-fields




### -field NtSecuritySharing

A UINT value that specifies whether the keyed mutex is shared or has a global <b>D3DKMT_HANDLE</b> kernel-mode handle to the resource.

If <b>NtSecuritySharing</b> is set to 1 (<b>TRUE</b>), the keyed mutex is shared using the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtshareobjects.md">D3DKMTShareObjects</a> function but does not have a global <b>D3DKMT_HANDLE</b> handle to the resource. In this case, the process handle to the resource is provided by the <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_createkeyedmutex2.md">D3DKMT_CREATEKEYEDMUTEX2</a>.<b>hKeyedMutex</b> member in a call to the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreatekeyedmutex2.md">D3DKMTCreateKeyedMutex2</a> function.

If <b>NtSecuritySharing</b> is set to zero (<b>FALSE</b>), the keyed mutex has a global <b>D3DKMT_HANDLE</b> handle to the resource provided by  the <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_createkeyedmutex2.md">D3DKMT_CREATEKEYEDMUTEX2</a>.<b>hSharedHandle</b> member in a call to <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreatekeyedmutex2.md">D3DKMTCreateKeyedMutex2</a>.


### -field Reserved

This member is reserved and should be set to zero. Setting this member is equivalent to setting the remaining 31 bits (0xFFFFFFFE) of a 32-bit value to zeros.


#### - Value

[in] A member in the union that <b>D3DKMT_CREATEKEYEDMUTEX2_FLAGS</b> contains that can hold a 32-bit value that identifies the keyed mutex  sharing type.


## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_createkeyedmutex2.md">D3DKMT_CREATEKEYEDMUTEX2</a>



<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtshareobjects.md">D3DKMTShareObjects</a>



<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreatekeyedmutex2.md">D3DKMTCreateKeyedMutex2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_CREATEKEYEDMUTEX2_FLAGS structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


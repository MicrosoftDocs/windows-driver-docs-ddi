---
UID: NS:d3dkmthk._D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME
title: "_D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME"
author: windows-driver-content
description: Describes information that is required to map a GDI display name to a remote video present network (VidPN) source ID.
old-location: display\d3dkmt_queryremotevidpnsourcefromgdidisplayname.htm
old-project: display
ms.assetid: ac0ec68a-1f2c-4a39-bf88-0e69d50b1279
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3dkmt_queryremotevidpnsourcefromgdidisplayname, d3dkmthk/D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME, D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME structure [Display Devices], D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME, _D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME
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
-	D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME
product: Windows
targetos: Windows
req.typenames: D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME
---

# _D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME structure


## -description


Describes information that is required to map a GDI display name to a remote video present network (VidPN) source ID.


## -syntax


````
typedef struct _D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME {
  WCHAR                          DeviceName[32];
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
} D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME;
````


## -struct-fields




### -field DeviceName

[in] The name of the GDI device on which to open an adapter instance.


### -field VidPnSourceId

[out] The zero-based video present network (VidPN) source identifier for the display device that is represented by the <b>DeviceName</b> member.


## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtqueryremotevidpnsourcefromgdidisplayname.md">D3DKMTQueryRemoteVidPnSourceFromGdiDisplayName</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


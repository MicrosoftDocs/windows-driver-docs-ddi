---
UID: NS:ntddvol._VOLUME_READ_PLEX_INPUT
title: _VOLUME_READ_PLEX_INPUT
author: windows-driver-content
description: This structure is used in conjunction with IOCTL_VOLUME_READ_PLEX to read data from a specific plex in a volume.
old-location: storage\volume_read_plex_input.htm
old-project: storage
ms.assetid: 1d53c658-9912-4912-a74f-f7b93367b9e2
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _VOLUME_READ_PLEX_INPUT, *PVOLUME_READ_PLEX_INPUT, VOLUME_READ_PLEX_INPUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddvol.h
req.include-header: Ntddvol.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: VOLUME_READ_PLEX_INPUT
req.alt-loc: ntddvol.h
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
req.typenames: *PVOLUME_READ_PLEX_INPUT, VOLUME_READ_PLEX_INPUT
---

# _VOLUME_READ_PLEX_INPUT structure



## -description
This structure is used in conjunction with <a href="..\ntddvol\ni-ntddvol-ioctl_volume_read_plex.md">IOCTL_VOLUME_READ_PLEX</a> to read data from a specific <a href="wdkgloss.p#wdkgloss.plex#wdkgloss.plex"><i>plex</i></a> in a volume. 



## -syntax

````
typedef struct _VOLUME_READ_PLEX_INPUT {
  LARGE_INTEGER ByteOffset;
  ULONG         Length;
  ULONG         PlexNumber;
} VOLUME_READ_PLEX_INPUT, *PVOLUME_READ_PLEX_INPUT;
````


## -struct-fields

### -field ByteOffset

Supplies the start offset, in bytes, relative to the beginning of the volume. This member must be aligned on a 512-byte boundary. 


### -field Length

Supplies the length, in bytes, of the block to be read. This member must be an integer multiple of 512 bytes. 


### -field PlexNumber

Supplies the zero-based plex number. 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ntddvol\ni-ntddvol-ioctl_volume_read_plex.md">IOCTL_VOLUME_READ_PLEX</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20VOLUME_READ_PLEX_INPUT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


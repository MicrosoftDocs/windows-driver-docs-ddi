---
UID: NS:ntddchgr._CHANGER_READ_ELEMENT_STATUS
title: "_CHANGER_READ_ELEMENT_STATUS"
author: windows-driver-content
description: The CHANGER_READ_ELEMENT_STATUS structure is used in conjunction with the IOCTL_CHANGER_GET_ELEMENT_STATUS request to retrieve the status of all elements or the status of a specified number of elements of a particular type.
old-location: storage\changer_read_element_status.htm
old-project: storage
ms.assetid: 3e80790c-72b9-4e26-a767-a25e6425118e
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PCHANGER_READ_ELEMENT_STATUS, ,, A, C, CHANGER_READ_ELEMENT_STATUS, CHANGER_READ_ELEMENT_STATUS structure [Storage Devices], D, E, G, H, L, M, N, P, PCHANGER_READ_ELEMENT_STATUS, PCHANGER_READ_ELEMENT_STATUS structure pointer [Storage Devices], R, S, T, U, _, _CHANGER_READ_ELEMENT_STATUS, ntddchgr/CHANGER_READ_ELEMENT_STATUS, ntddchgr/PCHANGER_READ_ELEMENT_STATUS, storage.changer_read_element_status, structs-changer_bbb217cb-b38d-4d81-941f-ac1d78d0c584.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddchgr.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
-	ntddchgr.h
apiname:
-	CHANGER_READ_ELEMENT_STATUS
product: Windows
targetos: Windows
req.typenames: CHANGER_READ_ELEMENT_STATUS, *PCHANGER_READ_ELEMENT_STATUS
---

# _CHANGER_READ_ELEMENT_STATUS structure


## -description


The CHANGER_READ_ELEMENT_STATUS structure is used in conjunction with the <a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_get_element_status.md">IOCTL_CHANGER_GET_ELEMENT_STATUS</a> request to retrieve the status of all elements or the status of a specified number of elements of a particular type. 


## -syntax


````
typedef struct _CHANGER_READ_ELEMENT_STATUS {
  CHANGER_ELEMENT_LIST ElementList;
  BOOLEAN              VolumeTagInfo;
} CHANGER_READ_ELEMENT_STATUS, *PCHANGER_READ_ELEMENT_STATUS;
````


## -struct-fields




### -field ElementList

Specifies the element type and the number of elements of that type for which to report status in a structure of type <a href="..\ntddchgr\ns-ntddchgr-_changer_element_list.md">CHANGER_ELEMENT_LIST</a>. This member contains a list of structures of type <a href="..\ntddchgr\ns-ntddchgr-_changer_element.md">CHANGER_ELEMENT</a>. The <b>ElementType</b> member of each CHANGER_ELEMENT structure in this list can be assigned a value of <b>ChangerDrive</b>, <b>ChangerSlot</b>, <b>ChangerTransport</b>, <b>ChangerIEPort</b>, or <b>AllElements</b>. 


### -field VolumeTagInfo

Indicates, when <b>TRUE</b>, that volume tag information should be reported in addition to element status. When <b>FALSE</b>, it indicates that only element status should be reported. A volume tag can be a bar code or an application-defined value assigned using <a href="..\mcd\nf-mcd-changerqueryvolumetags.md">ChangerQueryVolumeTags</a>. This member is applicable only if either CHANGER_BAR_CODE_SCANNER_INSTALLED or CHANGER_VOLUME_IDENTIFICATION is set in the <b>Features0</b> member of the <a href="..\ntddchgr\ns-ntddchgr-_get_changer_parameters.md">GET_CHANGER_PARAMETERS</a> structure.


## -see-also

<a href="..\ntddchgr\ns-ntddchgr-_changer_element_list.md">CHANGER_ELEMENT_LIST</a>



<a href="..\ntddchgr\ns-ntddchgr-_changer_element.md">CHANGER_ELEMENT</a>



<a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_get_element_status.md">IOCTL_CHANGER_GET_ELEMENT_STATUS</a>



<a href="..\mcd\nf-mcd-changergetelementstatus.md">ChangerGetElementStatus</a>



<a href="..\ntddchgr\ns-ntddchgr-_get_changer_parameters.md">GET_CHANGER_PARAMETERS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CHANGER_READ_ELEMENT_STATUS structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


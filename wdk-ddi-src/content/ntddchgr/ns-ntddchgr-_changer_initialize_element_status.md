---
UID: NS:ntddchgr._CHANGER_INITIALIZE_ELEMENT_STATUS
title: "_CHANGER_INITIALIZE_ELEMENT_STATUS"
author: windows-driver-content
description: The CHANGER_INITIALIZE_ELEMENT_STATUS structure is used in conjunction with the IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS request to initialize the status of all elements or of a specified number of elements of a particular type.
old-location: storage\changer_initialize_element_status.htm
old-project: storage
ms.assetid: fd26a97d-cbea-4ab4-b54e-1831d6e3a8ed
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: CHANGER_INITIALIZE_ELEMENT_STATUS, storage.changer_initialize_element_status, _CHANGER_INITIALIZE_ELEMENT_STATUS, *PCHANGER_INITIALIZE_ELEMENT_STATUS, structs-changer_94235bd7-09e6-47a1-b30c-0d5d12ca7917.xml, CHANGER_INITIALIZE_ELEMENT_STATUS structure [Storage Devices], ntddchgr/CHANGER_INITIALIZE_ELEMENT_STATUS, ntddchgr/PCHANGER_INITIALIZE_ELEMENT_STATUS, PCHANGER_INITIALIZE_ELEMENT_STATUS structure pointer [Storage Devices], PCHANGER_INITIALIZE_ELEMENT_STATUS
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
-	CHANGER_INITIALIZE_ELEMENT_STATUS
product: Windows
targetos: Windows
req.typenames: "*PCHANGER_INITIALIZE_ELEMENT_STATUS, CHANGER_INITIALIZE_ELEMENT_STATUS"
---

# _CHANGER_INITIALIZE_ELEMENT_STATUS structure


## -description


The CHANGER_INITIALIZE_ELEMENT_STATUS structure is used in conjunction with the <a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_initialize_element_status.md">IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS</a> request to initialize the status of all elements or of a specified number of elements of a particular type. 


## -syntax


````
typedef struct _CHANGER_INITIALIZE_ELEMENT_STATUS {
  CHANGER_ELEMENT_LIST ElementList;
  BOOLEAN              BarCodeScan;
} CHANGER_INITIALIZE_ELEMENT_STATUS, *PCHANGER_INITIALIZE_ELEMENT_STATUS;
````


## -struct-fields




### -field ElementList

Contains a structure of type <a href="..\ntddchgr\ns-ntddchgr-_changer_element_list.md">CHANGER_ELEMENT_LIST</a> that specifies the element type and the number of elements. If the <b>Features0</b> member of the <a href="..\ntddchgr\ns-ntddchgr-_get_changer_parameters.md">GET_CHANGER_PARAMETERS</a> structure is set to CHANGER_INIT_ELEM_STAT_WITH_RANGE, the changer supports initializing a range of elements. In this case, the element type can be <b>ChangerTransport</b>, <b>ChangerSlot</b>, <b>ChangerDrive</b>, or <b>ChangerIEPort</b> and <b>ElementList</b> can specify a number of elements to initialize. Otherwise, the element type must be <b>AllElements</b> and the number of elements is ignored. 


### -field BarCodeScan

Instructs the changer driver, when <b>TRUE</b>, to initialize elements by scanning bar codes. When <b>FALSE</b>, the changer driver takes no action. This member is applicable only if the <b>Features0</b> member of GET_CHANGER_PARAMETERS is set to CHANGER_BAR_CODE_SCANNER_INSTALLED. If the changer has nonvolatile RAM, a bar code scan can serve as an optimization.


## -see-also

<a href="..\mcd\nf-mcd-changerinitializeelementstatus.md">ChangerInitializeElementStatus</a>



<a href="..\ntddchgr\ns-ntddchgr-_changer_element_list.md">CHANGER_ELEMENT_LIST</a>



<a href="..\ntddchgr\ns-ntddchgr-_get_changer_parameters.md">GET_CHANGER_PARAMETERS</a>



<a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_initialize_element_status.md">IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CHANGER_INITIALIZE_ELEMENT_STATUS structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


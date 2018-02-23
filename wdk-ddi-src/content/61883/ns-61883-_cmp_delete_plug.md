---
UID: NS:61883._CMP_DELETE_PLUG
title: "_CMP_DELETE_PLUG"
author: windows-driver-content
description: This structure is used to delete a plug.Av61883_CreatePlug.
old-location: ieee\cmp_delete_plug.htm
old-project: IEEE
ms.assetid: 93F81B97-5C37-47BF-8867-0FBEFA8F6D3B
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IEEE.cmp_delete_plug, PCMP_DELETE_PLUG, PCMP_DELETE_PLUG structure pointer [Buses], 61883/PCMP_DELETE_PLUG, _CMP_DELETE_PLUG, CMP_DELETE_PLUG, 61883/CMP_DELETE_PLUG, *PCMP_DELETE_PLUG, CMP_DELETE_PLUG structure [Buses]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 61883.h
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
-	61883.h
apiname:
-	CMP_DELETE_PLUG
product: Windows
targetos: Windows
req.typenames: CMP_DELETE_PLUG, *PCMP_DELETE_PLUG
---

# _CMP_DELETE_PLUG structure


## -description


This structure is used to delete a plug.The request deletes a plug control register (iPCR or oPCR) that was created with <a href="https://msdn.microsoft.com/library/windows/hardware/ff536961">Av61883_CreatePlug</a>. A driver is responsible for deleting all of the plugs it has created before the system unloads the driver.


## -syntax


````
typedef struct _CMP_DELETE_PLUG {
  HANDLE hPlug;
} CMP_DELETE_PLUG, *PCMP_DELETE_PLUG;
````


## -struct-fields




### -field hPlug

On input, a handle to the plug to delete.


## -remarks



If successful, the IEC-61883 protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_SUCCESS. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20CMP_DELETE_PLUG structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


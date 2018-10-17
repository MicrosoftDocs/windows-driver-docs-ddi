---
UID: NS:iscsiop._AddRADIUSServer_IN
title: "_AddRADIUSServer_IN"
author: windows-driver-content
description: The AddRADIUSServer_IN structure holds the input data for the AddRADIUSServer method, which is used to add a new RADIUS server entry to existing list.
old-location: storage\addradiusserver_in.htm
tech.root: storage
ms.assetid: 7b7b9f3b-df33-4886-bd22-23429cb05ea7
ms.date: 3/29/2018
ms.keywords: "*PAddRADIUSServer_IN, AddRADIUSServer_IN, AddRADIUSServer_IN structure [Storage Devices], PAddRADIUSServer_IN, PAddRADIUSServer_IN structure pointer [Storage Devices], _AddRADIUSServer_IN, iscsiop/AddRADIUSServer_IN, iscsiop/PAddRADIUSServer_IN, storage.addradiusserver_in, structs-iSCSI_9899ffb9-7e0d-4d1e-af4c-9dd771527610.xml"
ms.topic: struct
req.header: iscsiop.h
req.include-header: Iscsiop.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	iscsiop.h
api_name:
-	AddRADIUSServer_IN
product:
- Windows
targetos: Windows
req.typenames: AddRADIUSServer_IN, *PAddRADIUSServer_IN
---

# _AddRADIUSServer_IN structure


## -description


The AddRADIUSServer_IN structure holds the input data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550133">AddRADIUSServer</a> method, which is used to add a new RADIUS server entry to existing list.


## -struct-fields




### -field RADIUSIPAddress

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff561536">ISCSI_IP_Address</a> structure that contains an IP version-independent address of the RADIUS server.


## -remarks



It is optional that you implement this method.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550133">AddRADIUSServer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550135">AddRADIUSServer_OUT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561536">ISCSI_IP_Address</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563091">MSiSCSI_Operations WMI Class</a>
 

 


---
UID: NS:iscsiop._RemovePersistentLogin_IN
title: _RemovePersistentLogin_IN (iscsiop.h)
description: The RemovePersistentLogin_IN structure holds the input data for the RemovePersistentLogin method, which is used to remove persistent login information.
old-location: storage\removepersistentlogin_in.htm
tech.root: storage
ms.assetid: 94dc7a87-83a0-419d-914c-008d797fec87
ms.date: 03/29/2018
keywords: ["RemovePersistentLogin_IN structure"]
ms.keywords: "*PRemovePersistentLogin_IN, PRemovePersistentLogin_IN, PRemovePersistentLogin_IN structure pointer [Storage Devices], RemovePersistentLogin_IN, RemovePersistentLogin_IN structure [Storage Devices], _RemovePersistentLogin_IN, iscsiop/PRemovePersistentLogin_IN, iscsiop/RemovePersistentLogin_IN, storage.removepersistentlogin_in, structs-iSCSI_4972aa6c-a6a5-4409-a714-49693f679fa2.xml"
f1_keywords:
 - "iscsiop/RemovePersistentLogin_IN"
 - "RemovePersistentLogin_IN"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- iscsiop.h
api_name:
- RemovePersistentLogin_IN
targetos: Windows
req.typenames: RemovePersistentLogin_IN, *PRemovePersistentLogin_IN
---

# _RemovePersistentLogin_IN structure


## -description


The RemovePersistentLogin_IN structure holds the input data for the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/removepersistentlogin">RemovePersistentLogin</a> method, which is used to remove persistent login information.


## -struct-fields




### -field PortNumber

The port number from which the initiator established the logon session.


### -field TargetName

The iSCSI target name to be removed from the initiator's list of persistent logon targets.


### -field TargetPortal

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsidef/ns-iscsidef-_iscsi_targetportal">ISCSI_TargetPortal</a> structure that specifies the target portal for which the initiator should delete persistent logons. ISCSI_TargetPortal has an <b>Address</b> member of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsidef/ns-iscsidef-_iscsi_ip_address">ISCSI_IP_Address</a>. If the <b>Type</b> member of ISCSI_IP_Address is set to ISCSI_IP_ADDRESS_EMPTY, the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/removepersistentlogin">RemovePersistentLogin</a> method removes the persistent logons to the target for all portals.


## -remarks



You must implement this method.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsidef/ns-iscsidef-_iscsi_ip_address">ISCSI_IP_Address</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsidef/ns-iscsidef-_iscsi_targetportal">ISCSI_TargetPortal</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/removepersistentlogin">RemovePersistentLogin</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsiop/ns-iscsiop-_removepersistentlogin_out">RemovePersistentLogin_OUT</a>
 

 


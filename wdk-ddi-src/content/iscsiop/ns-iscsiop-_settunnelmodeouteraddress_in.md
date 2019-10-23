---
UID: NS:iscsiop._SetTunnelModeOuterAddress_IN
title: _SetTunnelModeOuterAddress_IN (iscsiop.h)
description: The SetTunnelModeOuterAddress_IN structure holds the input data for the SetTunnelModeOuterAddress method.
old-location: storage\settunnelmodeouteraddress_in.htm
tech.root: storage
ms.assetid: 3f698252-213f-482c-8c8f-624f0c370705
ms.date: 03/29/2018
ms.keywords: "*PSetTunnelModeOuterAddress_IN, PSetTunnelModeOuterAddress_IN, PSetTunnelModeOuterAddress_IN structure pointer [Storage Devices], SetTunnelModeOuterAddress_IN, SetTunnelModeOuterAddress_IN structure [Storage Devices], _SetTunnelModeOuterAddress_IN, iscsiop/PSetTunnelModeOuterAddress_IN, iscsiop/SetTunnelModeOuterAddress_IN, storage.settunnelmodeouteraddress_in, structs-iSCSI_d86148f6-e3d0-42b3-9e1d-3f341545f0b8.xml"
ms.topic: struct
f1_keywords:
 - "iscsiop/SetTunnelModeOuterAddress_IN"
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
- SetTunnelModeOuterAddress_IN
product:
- Windows
targetos: Windows
req.typenames: SetTunnelModeOuterAddress_IN, *PSetTunnelModeOuterAddress_IN
---

# _SetTunnelModeOuterAddress_IN structure


## -description


The SetTunnelModeOuterAddress_IN structure holds the input data for the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/settunnelmodeouteraddress">SetTunnelModeOuterAddress</a> method.


## -struct-fields




### -field PortNumber

The number of the port to associate with the tunnel-mode address. A value of 0xffffffff associates the tunnel-mode address with all ports.


### -field DestinationAddress

An <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsidef/ns-iscsidef-_iscsi_ip_address">ISCSI_IP_Address</a> structure that indicates the destination IP address in a way that is independent of the version of IP protocol in use.  


### -field TunnelModeOuterAddress

An ISCSI_IP_Address structure that indicates the IP address of the security gateway (tunnel-mode outer address) in a way that is independent of the version of IP protocol in use.


## -remarks



You must implement this method.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsidef/ns-iscsidef-_iscsi_ip_address">ISCSI_IP_Address</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/settunnelmodeouteraddress">SetTunnelModeOuterAddress</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsiop/ns-iscsiop-_settunnelmodeouteraddress_out">SetTunnelModeOuterAddress_OUT</a>
 

 


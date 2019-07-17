---
UID: NS:iscsifnd._ISCSI_DiscoveredTargetPortal2
title: _ISCSI_DiscoveredTargetPortal2 (iscsifnd.h)
description: The ISCSI_DiscoveredTargetPortal2 structure provides information that is associated with a discovered target portal.
old-location: storage\iscsi_discoveredtargetportal2.htm
tech.root: storage
ms.assetid: 68128d39-2490-4c6b-8780-e5aa542a4e3d
ms.date: 03/29/2018
ms.keywords: "*PISCSI_DiscoveredTargetPortal2, ISCSI_DiscoveredTargetPortal2, ISCSI_DiscoveredTargetPortal2 structure [Storage Devices], PISCSI_DiscoveredTargetPortal2, PISCSI_DiscoveredTargetPortal2 structure pointer [Storage Devices], _ISCSI_DiscoveredTargetPortal2, iscsifnd/ISCSI_DiscoveredTargetPortal2, iscsifnd/PISCSI_DiscoveredTargetPortal2, storage.iscsi_discoveredtargetportal2, structs-iSCSI_bbb760ce-7dc5-4f04-880e-3ff53921ed78.xml"
ms.topic: struct
f1_keywords:
 - "iscsifnd/ISCSI_DiscoveredTargetPortal2"
req.header: iscsifnd.h
req.include-header: Iscsifnd.h
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
- iscsifnd.h
api_name:
- ISCSI_DiscoveredTargetPortal2
product:
- Windows
targetos: Windows
req.typenames: ISCSI_DiscoveredTargetPortal2, *PISCSI_DiscoveredTargetPortal2
---

# _ISCSI_DiscoveredTargetPortal2 structure


## -description


The ISCSI_DiscoveredTargetPortal2 structure provides information that is associated with a discovered target portal. 


## -struct-fields




### -field Socket

The socket number of the portal. 


### -field Address

The network address of the portal. 


### -field SecurityBitmap

A bitmap, which is defined in the <i>iSNS specification</i>, that indicates the security characteristics of logon connections that are made to this target portal. The following table describes possible security flag values. 

<table>
<tr>
<th>Security flags</th>
<th>Meaning</th>
</tr>
<tr>
<td>
ISCSI_SECURITY_FLAG_TUNNEL_MODE_PREFERRED

</td>
<td>
The initiator HBA should log on targets by using IPsec tunnel mode. If this bit is not set IPsec tunnel mode is not required. 

</td>
</tr>
<tr>
<td>
ISCSI_SECURITY_FLAG_TRANSPORT_MODE_PREFERRED

</td>
<td>
The initiator HBA should log on targets by using IPsec transport mode. If this bit is not set IPsec transport mode is not required. 

</td>
</tr>
<tr>
<td>
ISCSI_SECURITY_FLAG_PFS_ENABLED

</td>
<td>
The initiator HBA should log on targets with Perfect Forward Secrecy (PFS) mode enabled; otherwise, the initiator HBA should make the session connection with PFS mode disabled. 

</td>
</tr>
<tr>
<td>
ISCSI_SECURITY_FLAG_AGGRESSIVE_MODE_ENABLED

</td>
<td>
The initiator HBA should log on targets with aggressive mode enabled. If this bit is not set the initiator HBA should make the session connection with aggressive mode disabled.

</td>
</tr>
<tr>
<td>
ISCSI_SECURITY_FLAG_MAIN_MODE_ENABLED

</td>
<td>
The initiator HBA should log on targets with main mode enabled. If this bit is not set the initiator HBA should make the session connection with main mode disabled. 

</td>
</tr>
<tr>
<td>
ISCSI_SECURITY_FLAG_IKE_IPSEC_ENABLED

</td>
<td>
The initiator HBA should log on targets with the IKE/IPsec protocol enabled. If this bit is not set the IKE/IPsec protocol is disabled.

</td>
</tr>
<tr>
<td>
ISCSI_SECURITY_FLAG_VALID

</td>
<td>
The other mask values are valid. If this bit is not set security flags are not specified.. 

</td>
</tr>
</table>
 

For more information about how to configure the default security characteristics that are assigned of the target portal in the registry, see the Remarks section.


### -field KeySize

The size, in bytes, of the encryption key in the <b>Key</b> member.


### -field Key

A variable-length array of characters that contains the encryption key that is associated with the portal address.


## -remarks



The ISCSI_DiscoveredTargetPortal2 structure is a superset of the information that is provided by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/iscsifnd/ns-iscsifnd-_iscsi_discoveredtargetportal">ISCSI_DiscoveredTargetPortal</a> structure, which only defines the target portal address. In addition to the network address of the target portal, the ISCSI_DiscoveredTargetPortal2 structure contains information about the target portal's security characteristics.

If the iSNS server does not assign a security bitmap to the target portal, the operating system associates the bitmap in the <b>DefaultSecurityBitmap</b> registry value with the portal. The <b>DefaultSecurityBitmap</b> registry value is located under the following registry key: <b>HKLM\Software\Microsoft\Windows NT\Current Version\ISCSI\Discovery Values</b>. 

The default security bitmap is useful in cases where the target portal is configured for IPsec but does not support iSNS. 

In general, management applications should use the iSCSI client PSKey command to configure the security bitmap for a target portal. But if there are a large number of portals that have the same security bitmap, the default security bitmap is a good way to automatically assign the same bitmap to all portals.

The WMI tool suite automatically generates a declaration of the ISCSI_DiscoveredTargetPortal2 structure when it compiles the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/iscsi-discoveredtargetportal-wmi-class">ISCSI_DiscoveredTargetPortal WMI Class</a> in <i>Discover.mof</i>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/iscsifnd/ns-iscsifnd-_iscsi_discoveredtargetportal">ISCSI_DiscoveredTargetPortal</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/iscsi-discoveredtargetportal-wmi-class">ISCSI_DiscoveredTargetPortal WMI Class</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/iscsidef/ns-iscsidef-_iscsi_targetportal">ISCSI_TargetPortal</a>
 

 


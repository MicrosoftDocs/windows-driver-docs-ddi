---
UID: NS:ndis._NDIS_PD_PROVIDER_DISPATCH
title: "_NDIS_PD_PROVIDER_DISPATCH"
author: windows-driver-content
description: This structure is used as input for the OID_PD_OPEN_PROVIDER and serves as a container for all the provider's driver routines.
old-location: netvista\ndis_pd_provider_dispatch.htm
old-project: netvista
ms.assetid: E93B8A07-7C06-470B-9B26-8D59C2685D2C
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NDIS_PD_PROVIDER_DISPATCH, NDIS_PD_PROVIDER_DISPATCH structure [Network Drivers Starting with Windows Vista], PNDIS_PD_PROVIDER_DISPATCH, PNDIS_PD_PROVIDER_DISPATCH structure pointer [Network Drivers Starting with Windows Vista], _NDIS_PD_PROVIDER_DISPATCH, ndis/NDIS_PD_PROVIDER_DISPATCH, ndis/PNDIS_PD_PROVIDER_DISPATCH, netvista.ndis_pd_provider_dispatch
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.irql: See Remarks section
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ndis.h
api_name:
-	NDIS_PD_PROVIDER_DISPATCH
product: Windows
targetos: Windows
req.typenames: NDIS_PD_PROVIDER_DISPATCH
---

# _NDIS_PD_PROVIDER_DISPATCH structure


## -description


This structure is used as input for the <a href="https://msdn.microsoft.com/library/windows/hardware/dn931852">OID_PD_OPEN_PROVIDER</a> and serves as a container for all the provider's driver routines.


## -struct-fields




### -field Header

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the <b>NDIS_PD_PROVIDER_DISPATCH</b> structure. Set the members of this structure as follows:

<ul>
<li><b>Type</b> = <b>NDIS_OBJECT_TYPE_DEFAULT</b></li>
<li><b>Revision</b> = <b>NDIS_PD_PROVIDER_DISPATCH_REVISION_1</b></li>
<li><b>Size</b> = <b>NDIS_SIZEOF_PD_PROVIDER_DISPATCH_REVISION_1</b></li>
</ul>

### -field Flags

This member is reserved and must be set to 0 by the provider.


### -field NdisPDAllocateQueue

See <a href="https://msdn.microsoft.com/E9091C69-0E21-40CC-B3D3-1F770ABA0D47">NdisPDAllocateQueue</a>.


### -field NdisPDFreeQueue

See <a href="https://msdn.microsoft.com/1DE8582C-AF11-4CBA-8F4C-159266A7F3BA">NdisPDFreeQueue</a>.


### -field NdisPDAcquireReceiveQueues

 


### -field NdisPDReleaseReceiveQueues

 


### -field NdisPDAllocateCounter

See <a href="https://msdn.microsoft.com/86AA537D-952F-4A7A-ACA4-24B8C1AE932A">NdisPDAllocateCounter</a>.


### -field NdisPDFreeCounter

See <a href="https://msdn.microsoft.com/60C47437-A999-4F82-B144-6F77410E5C07">NdisPDFreeCounter</a>.


### -field NdisPDQueryCounter

See <a href="https://msdn.microsoft.com/C4860A43-2C53-4967-81A8-41FFF5CD2A5E">NdisPDQueryCounter</a>.


### -field NdisPDSetReceiveFilter

See <a href="https://msdn.microsoft.com/49587142-9C84-4F73-BE0C-D256A8E6BF4B">NdisPDSetReceiveFilter</a>.


### -field NdisPDClearReceiveFilter

See <a href="https://msdn.microsoft.com/C91F2E5D-C37F-48A9-9AE0-F5A8C5D8F54D">NdisPDClearReceiveFilter</a>.


### -field NdisPDRequestDrainNotification

 


### -field NdisPDQueueControl

 


### -field NdisPDProviderControl

 




#### - NdisPDOffRssReceiveQueues

See <a href="https://msdn.microsoft.com/library/windows/hardware/dn931860(d=robot)">NdisPDOffRssReceiveQueues</a>.


#### - NdisPDOnRssReceiveQueues

See <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt808524(d=robot)">NdisPDOnRssReceiveQueues</a>.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_PD_PROVIDER_DISPATCH structure%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes

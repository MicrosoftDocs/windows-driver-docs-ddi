---
UID: NS:windot11.DOT11_ROAMING_COMPLETION_PARAMETERS
title: DOT11_ROAMING_COMPLETION_PARAMETERS
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_roaming_completion_parameters.htm
old-project: netvista
ms.assetid: 535857c5-dd71-4575-8475-ff6c7c934dbe
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: DOT11_ROAMING_COMPLETION_PARAMETERS, DOT11_ROAMING_COMPLETION_PARAMETERS, *PDOT11_ROAMING_COMPLETION_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_ROAMING_COMPLETION_PARAMETERS
req.alt-loc: windot11.h
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
req.typenames: DOT11_ROAMING_COMPLETION_PARAMETERS, *PDOT11_ROAMING_COMPLETION_PARAMETERS
req.product: Windows 10 or later.
---

# DOT11_ROAMING_COMPLETION_PARAMETERS structure



## -description

## -syntax

````
typedef struct DOT11_ROAMING_COMPLETION_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  DOT11_ASSOC_STATUS uStatus;
} DOT11_ROAMING_COMPLETION_PARAMETERS, *PDOT11_ROAMING_COMPLETION_PARAMETERS;
````


## -struct-fields

### -field Header

The type, revision, and size of the DOT11_ROAMING_COMPLETION_PARAMETERS structure. This member is
     formatted as an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.
     

The miniport driver must set the members of 
     <i>Header</i> to the following values:




### -field Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.


### -field Revision

This member must be set to DOT11_ROAMING_COMPLETION_PARAMETERS_REVISION_1.


### -field Size

This member must be set to 
       <code>sizeof(DOT11_ROAMING_COMPLETION_PARAMETERS)</code>.

</dd>
</dl>
For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field uStatus

The completion status of the roaming operation formatted as a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff547652">DOT11_ASSOC_STATUS</a> value.


## -remarks
For more information about the roaming operation, see 
    <a href="https://msdn.microsoft.com/b52e134e-4f26-4797-af57-dd7da177c193">Roaming Operations</a>.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547652">DOT11_ASSOC_STATUS</a>
</dt>
<dt>
<a href="netvista.ndis_status_dot11_roaming_completion">
   NDIS_STATUS_DOT11_ROAMING_COMPLETION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_ROAMING_COMPLETION_PARAMETERS structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


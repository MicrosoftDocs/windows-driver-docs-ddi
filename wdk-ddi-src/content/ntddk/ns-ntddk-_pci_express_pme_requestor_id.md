---
UID: NS:ntddk._PCI_EXPRESS_PME_REQUESTOR_ID
title: "_PCI_EXPRESS_PME_REQUESTOR_ID"
author: windows-driver-content
description: The PCI_EXPRESS_PME_REQUESTOR_ID structure describes the identifier of the requester of a power management event (PME).
old-location: pci\pci_express_pme_requestor_id.htm
old-project: PCI
ms.assetid: 2305ffbd-22c8-4f63-bbe4-fd297bf98e39
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *PPCI_EXPRESS_PME_REQUESTOR_ID, ,, C, D, E, I, M, O, P, PCI.pci_express_pme_requestor_id, PCI_EXPRESS_PME_REQUESTOR_ID, PCI_EXPRESS_PME_REQUESTOR_ID union [Buses], PPCI_EXPRESS_PME_REQUESTOR_ID, PPCI_EXPRESS_PME_REQUESTOR_ID union pointer [Buses], Q, R, S, T, U, X, _, _PCI_EXPRESS_PME_REQUESTOR_ID, ntddk/PCI_EXPRESS_PME_REQUESTOR_ID, ntddk/PPCI_EXPRESS_PME_REQUESTOR_ID, pci_struct_0cb11d1f-7426-42fc-9d77-373516a492ae.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h, Miniport.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	PCI_EXPRESS_PME_REQUESTOR_ID
product: Windows
targetos: Windows
req.typenames: PCI_EXPRESS_PME_REQUESTOR_ID, *PPCI_EXPRESS_PME_REQUESTOR_ID
---

# _PCI_EXPRESS_PME_REQUESTOR_ID structure


## -description


The PCI_EXPRESS_PME_REQUESTOR_ID structure describes the identifier of the requester of a power management event (PME).


## -syntax


````
typedef union _PCI_EXPRESS_PME_REQUESTOR_ID {
  struct {
    USHORT FunctionNumber  :3;
    USHORT DeviceNumber  :5;
    USHORT BusNumber  :3;
  };
  USHORT AsUSHORT;
} PCI_EXPRESS_PME_REQUESTOR_ID, *PPCI_EXPRESS_PME_REQUESTOR_ID;
````


## -struct-fields




### -field DUMMYSTRUCTNAME

 


### -field AsUSHORT

A USHORT representation of the contents of the PCI_EXPRESS_PME_REQUESTOR_ID structure.


#### - FunctionNumber

The function number of the requester.


#### - DeviceNumber

The device number of the requester.


#### - BusNumber

The bus number of the requester.


## -remarks



The PCI_EXPRESS_PME_REQUESTOR_ID structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_PME_REQUESTOR_ID structure is contained in the <b>PMERequestorId</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537477">PCI_EXPRESS_ROOT_STATUS_REGISTER</a> structure.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537477">PCI_EXPRESS_ROOT_STATUS_REGISTER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20PCI_EXPRESS_PME_REQUESTOR_ID union%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


---
UID: NS:wdm._PCI_EXPRESS_CORRECTABLE_ERROR_MASK
title: "_PCI_EXPRESS_CORRECTABLE_ERROR_MASK"
author: windows-driver-content
description: The PCI_EXPRESS_CORRECTABLE_ERROR_MASK structure describes a PCI Express (PCIe) correctable error mask register of a PCIe advanced error reporting capability structure.
old-location: pci\pci_express_correctable_error_mask.htm
old-project: PCI
ms.assetid: d666cdd3-a673-4105-b982-e7cc942131ee
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: PCI_EXPRESS_CORRECTABLE_ERROR_MASK union [Buses], pci_struct_770185be-12f9-4519-8077-6d90e8344590.xml, wdm/PPCI_CORRECTABLE_ERROR_MASK, *PPCI_CORRECTABLE_ERROR_MASK, wdm/PCI_EXPRESS_CORRECTABLE_ERROR_MASK, PPCI_CORRECTABLE_ERROR_MASK, PCI.pci_express_correctable_error_mask, _PCI_EXPRESS_CORRECTABLE_ERROR_MASK, PPCI_CORRECTABLE_ERROR_MASK union pointer [Buses], PCI_EXPRESS_CORRECTABLE_ERROR_MASK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Ntddk.h, Wdm.h
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdm.h
apiname:
-	PCI_EXPRESS_CORRECTABLE_ERROR_MASK
product: Windows
targetos: Windows
req.typenames: PCI_EXPRESS_CORRECTABLE_ERROR_MASK, *PPCI_CORRECTABLE_ERROR_MASK
req.product: Windows 10 or later.
---

# _PCI_EXPRESS_CORRECTABLE_ERROR_MASK structure


## -description


The PCI_EXPRESS_CORRECTABLE_ERROR_MASK structure describes a PCI Express (PCIe) correctable error mask register of a PCIe advanced error reporting capability structure.


## -syntax


````
typedef union _PCI_EXPRESS_CORRECTABLE_ERROR_MASK {
  struct {
    ULONG ReceiverError  :1;
    ULONG Reserved1  :5;
    ULONG BadTLP  :1;
    ULONG BadDLLP  :1;
    ULONG ReplayNumRollover  :1;
    ULONG Reserved2  :3;
    ULONG ReplayTimerTimeout  :1;
    ULONG AdvisoryNonFatalError  :1;
    ULONG Reserved3  :18;
  };
  ULONG  AsULONG;
} PCI_EXPRESS_CORRECTABLE_ERROR_MASK, *PPCI_CORRECTABLE_ERROR_MASK;
````


## -struct-fields




### -field DUMMYSTRUCTNAME

 


### -field DUMMYSTRUCTNAME.ReceiverError

 


### -field DUMMYSTRUCTNAME.Reserved1

 


### -field DUMMYSTRUCTNAME.BadTLP

 


### -field DUMMYSTRUCTNAME.BadDLLP

 


### -field DUMMYSTRUCTNAME.ReplayNumRollover

 


### -field DUMMYSTRUCTNAME.Reserved2

 


### -field DUMMYSTRUCTNAME.ReplayTimerTimeout

 


### -field DUMMYSTRUCTNAME.AdvisoryNonFatalError

 


### -field DUMMYSTRUCTNAME.CorrectedInternalError

 


### -field DUMMYSTRUCTNAME.HeaderLogOverflow

 


### -field DUMMYSTRUCTNAME.Reserved3

 


### -field AsULONG

A ULONG representation of the contents of the PCI_EXPRESS_CORRECTABLE_ERROR_MASK structure.


#### - ReceiverError

A single bit that indicates that the reporting of receiver errors is masked.


#### - Reserved1

Reserved.


#### - BadTLP

A single bit that indicates that the reporting of bad transaction layer packets (TLPs) is masked.


#### - BadDLLP

A single bit that indicates that the reporting of bad data link layer packets (DLLPs) is masked.


#### - ReplayNumRollover

A single bit that indicates that the reporting of rollovers of the counter that counts the number of times the retry buffer has been re-transmitted is masked.


#### - Reserved2

Reserved.


#### - ReplayTimerTimeout

A single bit that indicates that the reporting of timeouts of the replay timer is masked.


#### - AdvisoryNonFatalError

A single bit that indicates that the reporting of advisory non-fatal errors is masked.


#### - Reserved3

Reserved.


## -remarks


The PCI_EXPRESS_CORRECTABLE_ERROR_MASK structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_CORRECTABLE_ERROR_MASK structure is contained in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537457">PCI_EXPRESS_AER_CAPABILITY</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff537458">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff537472">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a> structures.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537472">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537458">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537457">PCI_EXPRESS_AER_CAPABILITY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20PCI_EXPRESS_CORRECTABLE_ERROR_MASK union%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


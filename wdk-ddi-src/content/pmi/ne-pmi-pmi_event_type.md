---
UID: NE:pmi.__unnamed_enum_4
title: PMI_EVENT_TYPE (pmi.h)
description: The PMI_EVENT_TYPE enumeration defines the type of PMI power meter event that is returned through the successful completion of an IOCTL_PMI_REGISTER_EVENT_NOTIFY request.
old-location: powermeter\pmi_event_type.htm
tech.root: powermeter
ms.assetid: c2a8422d-15f0-45df-bc54-946fb3d11a22
ms.date: 05/08/2018
ms.keywords: PMI_EVENT_TYPE, PMI_EVENT_TYPE enumeration [Power Metering and Budgeting Devices], PmiAveragingIntervalChangedEvent, PmiBudgetEvent, PmiCapabilitiesChangedEvent, PmiConfigurationChangedEvent, PmiEventMax, PmiThresholdEvent, PowerMeterRef_86ff4160-2977-4b72-a37f-72779df2d5dc.xml, pmi/PMI_EVENT_TYPE, pmi/PmiAveragingIntervalChangedEvent, pmi/PmiBudgetEvent, pmi/PmiCapabilitiesChangedEvent, pmi/PmiConfigurationChangedEvent, pmi/PmiEventMax, pmi/PmiThresholdEvent, powermeter.pmi_event_type
ms.topic: enum
f1_keywords:
 - "pmi/PMI_EVENT_TYPE"
req.header: pmi.h
req.include-header: Pmi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7, Windows Server 2008 R2, and later versions of the Windows operating systems.
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
- pmi.h
api_name:
- PMI_EVENT_TYPE
product:
- Windows
targetos: Windows
req.typenames: PMI_EVENT_TYPE
---

# PMI_EVENT_TYPE enumeration


## -description


The PMI_EVENT_TYPE enumeration defines the type of PMI power meter event that is returned through the successful completion of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ni-pmi-ioctl_pmi_register_event_notify">IOCTL_PMI_REGISTER_EVENT_NOTIFY</a> request.


## -enum-fields




### -field PmiCapabilitiesChangedEvent

The event was caused by a change in the PMI capabilities of the power meter.


### -field PmiThresholdEvent

The event was caused because the power level exceeded a configured threshold of the power meter.


### -field PmiConfigurationChangedEvent

The event was caused by a change in the PMI configuration of the power meter.


### -field PmiBudgetEvent

The event was caused because the power budget exceeded or fell below the configured budget of the power meter.


### -field PmiAveragingIntervalChangedEvent

The event was caused because the interval, during which the power meter averages power measurement data, was changed.


### -field PmiEventMax

The maximum number of PMI event types.


## -remarks



The <b>EventType</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_event">PMI_EVENT</a> structure contains information about the type of PMI event data that is referenced by the <b>Event</b> member of that structure. This structure is returned through a successful completion of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ni-pmi-ioctl_pmi_register_event_notify">IOCTL_PMI_REGISTER_EVENT_NOTIFY</a> request.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ni-pmi-ioctl_pmi_register_event_notify">IOCTL_PMI_REGISTER_EVENT_NOTIFY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_event">PMI_EVENT</a>
 

 


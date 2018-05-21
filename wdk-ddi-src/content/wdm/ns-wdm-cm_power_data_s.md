---
UID: NS:wdm.CM_Power_Data_s
title: CM_Power_Data_s
author: windows-driver-content
description: The CM_POWER_DATA structure contains information about a device's power management state and capabilities.
old-location: kernel\cm_power_data.htm
old-project: kernel
ms.assetid: 38fea22b-4d9a-4b03-bbb7-c22578f60def
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: "*PCM_POWER_DATA, CM_POWER_DATA, CM_POWER_DATA structure [Kernel-Mode Driver Architecture], CM_Power_Data_s, PCM_POWER_DATA, PCM_POWER_DATA structure pointer [Kernel-Mode Driver Architecture], kernel.cm_power_data, kstruct_a_da572af5-5cb2-41f4-be3d-f2c1b715e4d7.xml, wdm/CM_POWER_DATA, wdm/PCM_POWER_DATA"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Ntddk.h, Ntpoapi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Microsoft Windows XP and later versions of the Windows operating system.
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
-	wdm.h
api_name:
-	CM_POWER_DATA
product:
- Windows
targetos: Windows
req.typenames: CM_POWER_DATA, *PCM_POWER_DATA
---

# CM_Power_Data_s structure


## -description


The <b>CM_POWER_DATA</b> structure contains information about a device's power management state and capabilities.


## -struct-fields




### -field PD_Size

The size, in bytes, of this structure.


### -field PD_MostRecentPowerState

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff554628">DEVICE_POWER_STATE</a> value representing the device's most recent power state.


### -field PD_Capabilities

The device's power capabilities, represented by a combination of the following bit flags:

PDCAP_D0_SUPPORTED

PDCAP_D1_SUPPORTED

PDCAP_D2_SUPPORTED

PDCAP_D3_SUPPORTED

PDCAP_WAKE_FROM_D0_SUPPORTED

PDCAP_WAKE_FROM_D1_SUPPORTED

PDCAP_WAKE_FROM_D2_SUPPORTED

PDCAP_WAKE_FROM_D3_SUPPORTED

PDCAP_WARM_EJECT_SUPPORTED


### -field PD_D1Latency

The device's latency when returning the D0 state from the D1 state. For more information, see the <b>D1Latency</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff543095">DEVICE_CAPABILITIES</a>.


### -field PD_D2Latency

The device's latency when returning the D0 state from the D2 state. For more information, see the <b>D2Latency</b> member of <b>DEVICE_CAPABILITIES</b>.


### -field PD_D3Latency

The device's latency when returning the D0 state from the D3 state. For more information, see the <b>D3Latency</b> member of <b>DEVICE_CAPABILITIES</b>.


### -field PD_PowerStateMapping

An array of <b>DEVICE_POWER_STATE</b> values representing the maximum device power state achievable for each system power state. For more information, see the <b>DeviceState</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff543095">DEVICE_CAPABILITIES</a>.


### -field PD_DeepestSystemWake

Specifies the least-powered system state from which the device can wake the system. <b>PD_DeepestSystemWake</b> typically indicates one of the system sleeping states, S1, S2, or S3 (as specified by <b>PowerSystemSleeping1</b>, <b>PowerSystemSleeping2</b>, and <b>PowerSystemSleeping3</b>, respectively). Note, however, that some devices might be able to wake the system from the system hibernate state, S4 (as specified by <b>PowerSystemHibernate</b>), or even from the system shutdown state, S5 (as specified by <b>PowerSystemShutdown</b>). 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543095">DEVICE_CAPABILITIES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554628">DEVICE_POWER_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551967">SetupDiGetDeviceRegistryProperty</a>
 

 


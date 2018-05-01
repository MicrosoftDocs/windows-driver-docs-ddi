---
UID: NF:ndis.NdisWriteConfiguration
title: NdisWriteConfiguration function
author: windows-driver-content
description: The NdisWriteConfiguration function writes a caller-supplied value for a specified entry into the registry. This function must be invoked serially with respect to itself and the NdisReadConfiguration function.
old-location: netvista\ndiswriteconfiguration.htm
old-project: netvista
ms.assetid: 63c94f4d-1c8c-43c2-ae58-993da42a80a4
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: NdisWriteConfiguration, NdisWriteConfiguration function [Network Drivers Starting with Windows Vista], ndis/NdisWriteConfiguration, ndis_configuration_ref_7d603433-49ed-46d5-8a57-000c06d83d4a.xml, netvista.ndiswriteconfiguration
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisWriteConfiguration (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisWriteConfiguration (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miscellaneous_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisWriteConfiguration
product: Windows
targetos: Windows
req.typenames: 
---

# NdisWriteConfiguration function


## -description


The 
  <b>NdisWriteConfiguration</b> function writes a caller-supplied value for a specified entry into the
  registry. This function must be invoked serially with respect to itself and the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564511">NdisReadConfiguration</a> function.


## -parameters




### -param Status [out]

A pointer to a caller-supplied variable in which this function returns the status of the call as
     one of the following:
     





#### NDIS_STATUS_SUCCESS

The supplied value at 
       <i>ParameterValue</i> was written into the registry. If this is a new entry, the name at 
       <i>Keyword</i> also was written into the registry.



#### NDIS_STATUS_NOT_SUPPORTED

The supplied 
       <b>ParameterType</b> is invalid.



#### NDIS_STATUS_RESOURCES

NDIS could not allocate resources, usually enough memory, to transfer the requested information
       to the registry.



#### NDIS_STATUS_FAILURE

The requested information could not be written.


### -param ConfigurationHandle [in]

The handle to a registry key that was returned by the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/hh975122">NdisOpenConfigurationEx</a>, 
     <a href="https://msdn.microsoft.com/e405853a-cf25-4214-82a9-bc3d76334413">
     NdisOpenConfigurationKeyByIndex</a>, or 
     <a href="https://msdn.microsoft.com/9ce7f40f-28f1-4303-9f7a-24ff1213bab1">
     NdisOpenConfigurationKeyByName</a> function.


### -param Keyword [in]

A pointer to an NDIS_STRING type describing a caller-supplied counted string, in the
     system-default character set, specifying the name of an entry for which to write the value. For
     Microsoft Windows 2000 and later drivers, this string contains Unicode characters. That is, for Windows
     2000 and later, NDIS defines the NDIS_STRING type as a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> type.


### -param ParameterValue [in]

Pointer to a caller-supplied 
     <a href="https://msdn.microsoft.com/80250799-4263-43c0-85d5-f1c1c1fb0bae">
     NDIS_CONFIGURATION_PARAMETER</a> structure.


## -returns



None




## -remarks



If an entry of the same name as at 
    <i>Keyword</i> already exists under the opened registry key, 
    <b>NdisWriteConfiguration</b> replaces its current value with the caller-supplied value. Otherwise, 
    <b>NdisWriteConfiguration</b> adds a new value entry with the given name and supplied value to the
    registry.

In the configuration registry of Windows 2000 and later versions, an NDIS 
    <i>Keyword</i> is a synonym for a
    <i>value entry name</i>. Such a name is a counted sequence of Unicode characters, terminated with a
    NUL.

<b>NdisWriteConfiguration</b> buffers and copies the caller-supplied string at 
    <i>Keyword</i> and the caller-supplied data specified at 
    <i>ParameterValue</i> . This memory is freed when the driver releases the 
    <i>ConfigurationHandle</i> with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561642">NdisCloseConfiguration</a> function.
    The caller of 
    <b>NdisWriteConfiguration</b> is responsible for releasing the buffered string at 
    <i>Keyword</i> and the memory allocated for the 
    <a href="https://msdn.microsoft.com/80250799-4263-43c0-85d5-f1c1c1fb0bae">
    NDIS_CONFIGURATION_PARAMETER</a> structure.

As an alternative to calling 
    <b>NdisWriteConfiguration</b>, every NDIS driver can set up configuration information in the registry for
    itself using the AddReg directive in the driver's INF file.

For more information about setup and installation files for Windows 2000 and later versions, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/install/overview-of-device-and-driver-installation">Device Installation
    Overview</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a>



<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564868">NDIS_CONFIGURATION_PARAMETER</a>



<a href="https://msdn.microsoft.com/8efdcf9f-df8c-4b3b-8b21-11a10a885322">
   NdisAnsiStringToUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561642">NdisCloseConfiguration</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562577">NdisFreeMemory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562604">NdisFreeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562730">NdisInitAnsiString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562745">NdisInitUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562741">NdisInitializeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh975122">NdisOpenConfigurationEx</a>



<a href="https://msdn.microsoft.com/e405853a-cf25-4214-82a9-bc3d76334413">
   NdisOpenConfigurationKeyByIndex</a>



<a href="https://msdn.microsoft.com/9ce7f40f-28f1-4303-9f7a-24ff1213bab1">
   NdisOpenConfigurationKeyByName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564511">NdisReadConfiguration</a>



<a href="https://msdn.microsoft.com/37ac55b8-093e-4bf4-9c66-05ab5fc7ebc9">
   NdisUnicodeStringToAnsiString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
 

 


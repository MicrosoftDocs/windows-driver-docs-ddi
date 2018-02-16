---
UID: NF:ndis.NdisWriteConfiguration
title: NdisWriteConfiguration function
author: windows-driver-content
description: The NdisWriteConfiguration function writes a caller-supplied value for a specified entry into the registry. This function must be invoked serially with respect to itself and the NdisReadConfiguration function.
old-location: netvista\ndiswriteconfiguration.htm
old-project: netvista
ms.assetid: 63c94f4d-1c8c-43c2-ae58-993da42a80a4
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ndis/NdisWriteConfiguration, netvista.ndiswriteconfiguration, ndis_configuration_ref_7d603433-49ed-46d5-8a57-000c06d83d4a.xml, NdisWriteConfiguration, NdisWriteConfiguration function [Network Drivers Starting with Windows Vista]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisWriteConfiguration
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---

# NdisWriteConfiguration function


## -description


The 
  <b>NdisWriteConfiguration</b> function writes a caller-supplied value for a specified entry into the
  registry. This function must be invoked serially with respect to itself and the <a href="..\ndis\nf-ndis-ndisreadconfiguration.md">NdisReadConfiguration</a> function.


## -syntax


````
VOID NdisWriteConfiguration(
  _Out_ PNDIS_STATUS                  Status,
  _In_  NDIS_HANDLE                   ConfigurationHandle,
  _In_  PNDIS_STRING                  Keyword,
  _In_  PNDIS_CONFIGURATION_PARAMETER ParameterValue
);
````


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
     <a href="..\ndis\nf-ndis-ndisopenconfigurationex.md">NdisOpenConfigurationEx</a>, 
     <a href="..\ndis\nf-ndis-ndisopenconfigurationkeybyindex.md">
     NdisOpenConfigurationKeyByIndex</a>, or 
     <a href="..\ndis\nf-ndis-ndisopenconfigurationkeybyname.md">
     NdisOpenConfigurationKeyByName</a> function.


### -param Keyword [in]

A pointer to an NDIS_STRING type describing a caller-supplied counted string, in the
     system-default character set, specifying the name of an entry for which to write the value. For
     Microsoft Windows 2000 and later drivers, this string contains Unicode characters. That is, for Windows
     2000 and later, NDIS defines the NDIS_STRING type as a 
     <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> type.


### -param ParameterValue [in]

Pointer to a caller-supplied 
     <a href="..\ndis\ns-ndis-_ndis_configuration_parameter.md">
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
    <a href="..\ndis\nf-ndis-ndiscloseconfiguration.md">NdisCloseConfiguration</a> function.
    The caller of 
    <b>NdisWriteConfiguration</b> is responsible for releasing the buffered string at 
    <i>Keyword</i> and the memory allocated for the 
    <a href="..\ndis\ns-ndis-_ndis_configuration_parameter.md">
    NDIS_CONFIGURATION_PARAMETER</a> structure.

As an alternative to calling 
    <b>NdisWriteConfiguration</b>, every NDIS driver can set up configuration information in the registry for
    itself using the AddReg directive in the driver's INF file.

For more information about setup and installation files for Windows 2000 and later versions, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/install/overview-of-device-and-driver-installation">Device Installation
    Overview</a>.




## -see-also

<a href="..\ndis\nf-ndis-ndisopenconfigurationkeybyindex.md">
   NdisOpenConfigurationKeyByIndex</a>



<a href="..\ndis\nf-ndis-ndisansistringtounicodestring.md">
   NdisAnsiStringToUnicodeString</a>



<a href="..\ndis\nf-ndis-ndisfreestring.md">NdisFreeString</a>



<a href="..\ndis\nf-ndis-ndisopenconfigurationkeybyname.md">
   NdisOpenConfigurationKeyByName</a>



<a href="..\ndis\nf-ndis-ndisinitializestring.md">NdisInitializeString</a>



<a href="..\ndis\nf-ndis-ndisunicodestringtoansistring.md">
   NdisUnicodeStringToAnsiString</a>



<a href="..\ndis\ns-ndis-_ndis_configuration_parameter.md">NDIS_CONFIGURATION_PARAMETER</a>



<a href="..\ndis\nf-ndis-ndisreadconfiguration.md">NdisReadConfiguration</a>



<a href="..\ndis\nf-ndis-ndisfreememory.md">NdisFreeMemory</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a>



<a href="..\ndis\nf-ndis-ndisinitunicodestring.md">NdisInitUnicodeString</a>



<a href="..\ndis\nf-ndis-ndiscloseconfiguration.md">NdisCloseConfiguration</a>



<a href="..\ndis\nf-ndis-ndisinitansistring.md">NdisInitAnsiString</a>



<a href="..\ndis\nf-ndis-ndisopenconfigurationex.md">NdisOpenConfigurationEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisWriteConfiguration function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


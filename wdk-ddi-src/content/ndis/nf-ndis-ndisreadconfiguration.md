---
UID: NF:ndis.NdisReadConfiguration
title: NdisReadConfiguration function (ndis.h)
description: The NdisReadConfiguration function returns the value of a named entry of the specified type from the registry, given the handle to an open registry key.
old-location: netvista\ndisreadconfiguration.htm
tech.root: netvista
ms.assetid: 74560229-9e97-40b9-961c-6bf726586e27
ms.date: 05/02/2018
keywords: ["NdisReadConfiguration function"]
ms.keywords: NDIS_STATUS_FAILURE, NDIS_STATUS_RESOURCES, NDIS_STATUS_SUCCESS, NdisReadConfiguration, NdisReadConfiguration function [Network Drivers Starting with Windows Vista], ndis/NdisReadConfiguration, ndis_configuration_ref_fb5d2879-b30e-470b-aa07-f5f5286973bf.xml, netvista.ndisreadconfiguration
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisReadConfiguration (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisReadConfiguration (NDIS   5.1)) in Windows XP.
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
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisReadConfiguration
 - ndis/NdisReadConfiguration
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisReadConfiguration
---

# NdisReadConfiguration function


## -description

The 
  <b>NdisReadConfiguration</b> function returns
  the value of a named entry of the specified type from the registry, given the handle to an open registry
  key. This function must be invoked serially with respect to itself and the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiswriteconfiguration">NdisWriteConfiguration</a> function.

## -parameters

### -param Status 

[out]
A pointer to a caller-supplied variable in which this function returns the status of the call as
     one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="NDIS_STATUS_SUCCESS"></a><a id="ndis_status_success"></a><dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The buffer at 
       <i>ParameterValue</i> contains the returned configuration information.

</td>
</tr>
<tr>
<td width="40%"><a id="NDIS_STATUS_RESOURCES"></a><a id="ndis_status_resources"></a><dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
NDIS could not allocate resources, usually enough memory, to return the requested
       information.

</td>
</tr>
<tr>
<td width="40%"><a id="NDIS_STATUS_FAILURE"></a><a id="ndis_status_failure"></a><dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
The requested information could not be found under the opened registry key designated by the 
       <i>ConfigurationHandle</i>.

</td>
</tr>
</table>

### -param ParameterValue 

[out]
A pointer to a memory location where NDIS supplies a pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_configuration_parameter">
     NDIS_CONFIGURATION_PARAMETER</a> structure if the call to 
     <b>NdisReadConfiguration</b> is
     successful. NDIS allocates memory for the 
     <b>
     NDIS_CONFIGURATION_PARAMETER</b> structure.

### -param ConfigurationHandle 

[in]
The handle to a registry key that was returned by the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ndis-ndisopenconfigurationex">NdisOpenConfigurationEx</a>, 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenconfigurationkeybyindex">
     NdisOpenConfigurationKeyByIndex</a>, or 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenconfigurationkeybyname">
     NdisOpenConfigurationKeyByName</a> function.

### -param Keyword 

[in]
A pointer to a caller-supplied NDIS_STRING type describing a counted string, in the system-default
     character set, specifying the name of the entry under the open registry key for which to return the
     value. 
     

Alternatively, pointer to a caller-supplied NDIS_STRING_CONSTANT specifying one of the following
     predefined entry names along with predefined return values:

<table>
<tr>
<th>Predefined Entry Name</th>
<th>Predefined Return Values</th>
</tr>
<tr>
<td>
ProcessorType

</td>
<td>

<ul>
<li>NdisProcessorX86</li>
<li>NdisProcessorAmd64</li>
<li>NdisProcessorIA64</li>
<li>NdisProcessorAlpha</li>
</ul> The following are possible only if an old (pre-NDIS 6.0) driver: 
        <ul>
<li>NdisProcessorMips</li>
<li>NdisProcessorPpc</li>
</ul>


</td>
</tr>
<tr>
<td>
NdisVersion

</td>
<td>
0xMMMMmmmm, where 
        <i>MMMM</i> is the major version and 
        <i>mmmm</i> is the minor version number. For example, 0x00050000 indicates that the highest NDIS
        version supported by the system is major version 5, minor version 0.

</td>
</tr>
</table>

### -param ParameterType 

[in]
The type of the value entry that is specified as one of the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ne-ndis-_ndis_parameter_type">NDIS_PARAMETER_TYPE</a> enumeration values.
     This parameter is ignored in Windows NT and later versions.

## -remarks

In the configuration registry of Windows 2000 and later versions, an NDIS 
    <i>keyword</i> is a synonym for a 
    <i>value entry name</i>. Such a name is a counted sequence of Unicode characters, terminated with a
    <b>NULL</b>.

Every NDIS driver can set up configuration information in the registry for itself using the 
    <b>AddReg</b> directive in its INF file. For example, a protocol driver might store its
    own name as an entry with a preformatted string value that can be passed in calls to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisregisterprotocoldriver">
    NdisRegisterProtocolDriver</a> function. For more information, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/add-registry-sections-in-a-network-inf-file">Add-registry-sections in
    a Network INF File</a>.

Each miniport driver also has associated value entries in the registry. The value entries for any
    particular miniport driver can be device-dependent in nature. For example, a miniport driver might have
    keywords such as *FlowControl, *SpeedDuplex, and *InterruptModeration. The value associated with such an
    NDIS keyword can be either an integer (ULONG-type) or a string (NDIS_STRING-type). For example, the set
    of possible values for the already mentioned *FlowControl entry might be <b>NdisParameterInteger</b> values 0,
    1, 2, or 3, or the equivalents in hexadecimal as <b>NdisParameterHexInteger</b> values.

NdisReadConfiguration buffers and copies the caller-supplied string at 
    <i>Keyword</i> and releases the storage it allocates for this copy before it returns control to the
    caller. The memory it allocates for the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_configuration_parameter">
    NDIS_CONFIGURATION_PARAMETER</a> structure is freed when the driver releases the ConfigurationHandle
    with the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscloseconfiguration">NdisCloseConfiguration</a> function.
    The caller of 
    <b>NdisReadConfiguration</b> is responsible
    for releasing the buffered string at 
    <i>Keyword</i>.

Note that NDIS does not validate values that a driver reads from the registry. The caller of 
    <b>NdisReadConfiguration</b> must therefore
    not make any assumptions about such values and must validate each value read from the registry. If the
    caller determines that a value is out of bounds, it should use a default value instead.

For more information about setup and installation files, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/install/overview-of-device-and-driver-installation">Device Installation
    Overview</a>.

## -see-also

<a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-string">ANSI_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_configuration_parameter">NDIS_CONFIGURATION_PARAMETER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ne-ndis-_ndis_parameter_type">NDIS_PARAMETER_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisansistringtounicodestring">
   NdisAnsiStringToUnicodeString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscloseconfiguration">NdisCloseConfiguration</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreestring">NdisFreeString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisinitansistring">NdisInitAnsiString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisinitunicodestring">NdisInitUnicodeString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisinitializestring">NdisInitializeString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ndis-ndisopenconfigurationex">NdisOpenConfigurationEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenconfigurationkeybyindex">
   NdisOpenConfigurationKeyByIndex</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenconfigurationkeybyname">
   NdisOpenConfigurationKeyByName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisreadnetworkaddress">NdisReadNetworkAddress</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisunicodestringtoansistring">
   NdisUnicodeStringToAnsiString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiswriteconfiguration">NdisWriteConfiguration</a>



<a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>


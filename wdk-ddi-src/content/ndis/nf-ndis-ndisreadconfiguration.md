---
UID: NF:ndis.NdisReadConfiguration
title: NdisReadConfiguration function
author: windows-driver-content
description: The NdisReadConfiguration function returns the value of a named entry of the specified type from the registry, given the handle to an open registry key.
old-location: netvista\ndisreadconfiguration.htm
old-project: netvista
ms.assetid: 74560229-9e97-40b9-961c-6bf726586e27
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NDIS_STATUS_FAILURE, NDIS_STATUS_SUCCESS, ndis_configuration_ref_fb5d2879-b30e-470b-aa07-f5f5286973bf.xml, ndis/NdisReadConfiguration, netvista.ndisreadconfiguration, NdisReadConfiguration function [Network Drivers Starting with Windows Vista], NdisReadConfiguration, NDIS_STATUS_RESOURCES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisReadConfiguration
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisReadConfiguration function


## -description


The 
  <b>NdisReadConfiguration</b> function returns
  the value of a named entry of the specified type from the registry, given the handle to an open registry
  key. This function must be invoked serially with respect to itself and the <a href="..\ndis\nf-ndis-ndiswriteconfiguration.md">NdisWriteConfiguration</a> function.


## -syntax


````
VOID NdisReadConfiguration(
  _Out_ PNDIS_STATUS                  Status,
  _Out_ PNDIS_CONFIGURATION_PARAMETER *ParameterValue,
  _In_  NDIS_HANDLE                   ConfigurationHandle,
  _In_  PNDIS_STRING                  Keyword,
  _In_  NDIS_PARAMETER_TYPE           ParameterType
);
````


## -parameters




#### - Status [out]

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


#### - ParameterValue [out]

A pointer to a memory location where NDIS supplies a pointer to an 
     <mshelp:link keywords="netvista.ndis_configuration_parameter" tabindex="0"><b>
     NDIS_CONFIGURATION_PARAMETER</b></mshelp:link> structure if the call to 
     <b>NdisReadConfiguration</b> is
     successful. NDIS allocates memory for the 
     <b>
     NDIS_CONFIGURATION_PARAMETER</b> structure.


#### - ConfigurationHandle [in]

The handle to a registry key that was returned by the 
     <a href="..\ndis\nf-ndis-ndisopenconfigurationex.md">NdisOpenConfigurationEx</a>, 
     <mshelp:link keywords="netvista.ndisopenconfigurationkeybyindex" tabindex="0"><b>
     NdisOpenConfigurationKeyByIndex</b></mshelp:link>, or 
     <mshelp:link keywords="netvista.ndisopenconfigurationkeybyname" tabindex="0"><b>
     NdisOpenConfigurationKeyByName</b></mshelp:link> function.


#### - Keyword [in]

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


#### - ParameterType [in]

The type of the value entry that is specified as one of the 
     <a href="..\ndis\ne-ndis-_ndis_parameter_type.md">NDIS_PARAMETER_TYPE</a> enumeration values.
     This parameter is ignored in Windows NT and later versions.


## -returns


None



## -remarks


In the configuration registry of Windows 2000 and later versions, an NDIS 
    <i>keyword</i> is a synonym for a 
    <i>value entry name</i>. Such a name is a counted sequence of Unicode characters, terminated with a
    <b>NULL</b>.

Every NDIS driver can set up configuration information in the registry for itself using the 
    <b>AddReg</b> directive in its INF file. For example, a protocol driver might store its
    own name as an entry with a preformatted string value that can be passed in calls to the 
    <mshelp:link keywords="netvista.ndisregisterprotocoldriver" tabindex="0"><b>
    NdisRegisterProtocolDriver</b></mshelp:link> function. For more information, see 
    <mshelp:link keywords="netvista.add_registry_sections_in_a_network_inf_file" tabindex="0">Add-registry-sections in
    a Network INF File</mshelp:link>.

Each miniport driver also has associated value entries in the registry. The value entries for any
    particular miniport driver can be device-dependent in nature. For example, a miniport driver might have
    keywords such as *FlowControl, *SpeedDuplex, and *InterruptModeration. The value associated with such an
    NDIS keyword can be either an integer (ULONG-type) or a string (NDIS_STRING-type). For example, the set
    of possible values for the already mentioned *FlowControl entry might be <b>NdisParameterInteger</b> values 0,
    1, 2, or 3, or the equivalents in hexadecimal as <b>NdisParameterHexInteger</b> values.

NdisReadConfiguration buffers and copies the caller-supplied string at 
    <i>Keyword</i> and releases the storage it allocates for this copy before it returns control to the
    caller. The memory it allocates for the 
    <mshelp:link keywords="netvista.ndis_configuration_parameter" tabindex="0"><b>
    NDIS_CONFIGURATION_PARAMETER</b></mshelp:link> structure is freed when the driver releases the ConfigurationHandle
    with the 
    <a href="..\ndis\nf-ndis-ndiscloseconfiguration.md">NdisCloseConfiguration</a> function.
    The caller of 
    <b>NdisReadConfiguration</b> is responsible
    for releasing the buffered string at 
    <i>Keyword</i>.

Note that NDIS does not validate values that a driver reads from the registry. The caller of 
    <b>NdisReadConfiguration</b> must therefore
    not make any assumptions about such values and must validate each value read from the registry. If the
    caller determines that a value is out of bounds, it should use a default value instead.

For more information about setup and installation files, see 
    <mshelp:link keywords="devinst.overview_of_device_and_driver_installation" tabindex="0">Device Installation
    Overview</mshelp:link>.



## -see-also

<a href="..\ndis\nf-ndis-ndisreadnetworkaddress.md">NdisReadNetworkAddress</a>

<a href="..\ndis\nf-ndis-ndisinitunicodestring.md">NdisInitUnicodeString</a>

<a href="..\ndis\nf-ndis-ndisopenconfigurationex.md">NdisOpenConfigurationEx</a>

<a href="..\ndis\ns-ndis-_ndis_configuration_parameter.md">NDIS_CONFIGURATION_PARAMETER</a>

<a href="..\ndis\nf-ndis-ndiscloseconfiguration.md">NdisCloseConfiguration</a>

<a href="..\ndis\ne-ndis-_ndis_parameter_type.md">NDIS_PARAMETER_TYPE</a>

<mshelp:link keywords="netvista.ndisunicodestringtoansistring" tabindex="0"><b>
   NdisUnicodeStringToAnsiString</b></mshelp:link>

<a href="..\ndis\nf-ndis-ndisinitializestring.md">NdisInitializeString</a>

<a href="..\ndis\nf-ndis-ndisfreestring.md">NdisFreeString</a>

<a href="..\ndis\nf-ndis-ndisinitansistring.md">NdisInitAnsiString</a>

<mshelp:link keywords="netvista.ndisopenconfigurationkeybyindex" tabindex="0"><b>
   NdisOpenConfigurationKeyByIndex</b></mshelp:link>

<mshelp:link keywords="netvista.ndisansistringtounicodestring" tabindex="0"><b>
   NdisAnsiStringToUnicodeString</b></mshelp:link>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a>

<mshelp:link keywords="netvista.ndisopenconfigurationkeybyname" tabindex="0"><b>
   NdisOpenConfigurationKeyByName</b></mshelp:link>

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>

<a href="..\ndis\nf-ndis-ndiswriteconfiguration.md">NdisWriteConfiguration</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisReadConfiguration function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


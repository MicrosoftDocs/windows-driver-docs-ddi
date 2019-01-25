---
UID: NS:ndis._NDIS_CONFIGURATION_PARAMETER
title: "_NDIS_CONFIGURATION_PARAMETER" (ndis.h)
description: The NDIS_CONFIGURATION_PARAMETER structure contains the data and type of a named entry in the registry.
old-location: netvista\ndis_configuration_parameter.htm
tech.root: netvista
ms.assetid: 80250799-4263-43c0-85d5-f1c1c1fb0bae
ms.date: 05/02/2018
ms.keywords: "*PNDIS_CONFIGURATION_PARAMETER, NDIS_CONFIGURATION_PARAMETER, NDIS_CONFIGURATION_PARAMETER structure [Network Drivers Starting with Windows Vista], PNDIS_CONFIGURATION_PARAMETER, PNDIS_CONFIGURATION_PARAMETER structure pointer [Network Drivers Starting with Windows Vista], _NDIS_CONFIGURATION_PARAMETER, ndis/NDIS_CONFIGURATION_PARAMETER, ndis/PNDIS_CONFIGURATION_PARAMETER, ndis_configuration_ref_14664bdb-06c7-4d27-b71b-d6a69f3e3396.xml, netvista.ndis_configuration_parameter"
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers in Windows Vista. Supported for NDIS   5.1 drivers in Windows XP.
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
-	ndis.h
api_name:
-	NDIS_CONFIGURATION_PARAMETER
product:
- Windows
targetos: Windows
req.typenames: NDIS_CONFIGURATION_PARAMETER, *PNDIS_CONFIGURATION_PARAMETER
---

# _NDIS_CONFIGURATION_PARAMETER structure


## -description


The NDIS_CONFIGURATION_PARAMETER structure contains the data and type of a named entry in the
  registry.


## -struct-fields




### -field ParameterType

The type of the parameter specified as one of the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566740">NDIS_PARAMETER_TYPE</a> enumeration values. 
     

For successful calls to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff564511">NdisReadConfiguration</a> function, the    
     <b>ParameterType</b> value matches the value at the 
     <i>ParameterType</i> parameter. However, when the 
     <i>ParameterType</i> parameter is 
     <b>NdisParameterHexInteger</b>, the resulting 
     <b>ParameterType</b> member value is 
     <b>NdisParameterInteger</b>.


### -field ParameterData

A union that contains the value of the given named entry. If ParameterType is a string type, this
      member is an NDIS_STRING type describing a counted string in the system-default character set. For
      Microsoft Windows 2000 and later drivers, such a string contains Unicode characters. That is, for
      Windows 2000 and later, NDIS defines the NDIS_STRING type as a 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> type.

This union contains the following members:


### -field ParameterData.IntegerData

A ULONG value that is used when the 
      <b>ParameterType</b> member is set to 
      <b>NdisParameterInteger</b> or 
      <b>NdisParameterHexInteger</b>.


### -field ParameterData.StringData

An NDIS_STRING value that is used when the 
      <b>ParameterType</b> member is set to 
      <b>NdisParameterString</b> or 
      <b>NdisParameterMultiString</b>.


### -field ParameterData.BinaryData

A 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff543838">BINARY_DATA</a> structure that is used when the 
      <b>ParameterType</b> member is set to 
      <b>NdisParameterBinary</b>.


## -remarks



To read parameters in the registry, an NDIS driver can call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564511">NdisReadConfiguration</a> function. If
    the call is successful, NDIS returns a pointer to an NDIS_CONFIGURATION_PARAMETER structure at the 
    <i>ParameterValue</i> parameter of 
    <b>NdisReadConfiguration</b>.

To write parameters to the registry, an NDIS driver can call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564659">NdisWriteConfiguration</a> function. In
    this case, the driver initializes an NDIS_CONFIGURATION_PARAMETER structure and passes it at the 
    <i>ParameterValue</i> parameter of 
    <b>NdisWriteConfiguration</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543838">BINARY_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566740">NDIS_PARAMETER_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564511">NdisReadConfiguration</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564659">NdisWriteConfiguration</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
 

 


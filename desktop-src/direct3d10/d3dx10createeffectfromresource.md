---
Description: Create an effect from a resource.
ms.assetid: 239a3b14-9eea-4a0f-96b5-3959b7be3e19
title: D3DX10CreateEffectFromResource function (D3DX10Async.h)
ms.topic: reference
ms.date: 05/31/2018
topic_type: 
- APIRef
- kbSyntax
api_name: 
- D3DX10CreateEffectFromResource
api_type: 
- HeaderDef
api_location: 
- D3DX10Async.h
---

# D3DX10CreateEffectFromResource function

Create an effect from a resource.

## Syntax


```C++
HRESULT D3DX10CreateEffectFromResource(
  _In_        HMODULE            hModule,
  _In_        LPCTSTR            pResourceName,
  _In_        LPCTSTR            pSrcFileName,
  _In_  const D3D10_SHADER_MACRO *pDefines,
  _In_        ID3D10Include      *pInclude,
  _In_        LPCSTR             pProfile,
  _In_        UINT               HLSLFlags,
  _In_        UINT               FXFlags,
  _In_        ID3D10Device       *pDevice,
  _In_        ID3D10EffectPool   *pEffectPool,
  _In_        ID3DX10ThreadPump  *pPump,
  _Out_       ID3D10Effect       **ppEffect,
  _Out_       ID3D10Blob         **ppErrors,
  _Out_       HRESULT            *pHResult
);
```



## Parameters

<dl> <dt>

*hModule* \[in\]
</dt> <dd>

Type: **[**HMODULE**](../winprog/windows-data-types.md)**

A handle to the resource module containing the effect. HMODULE can be obtained with [GetModuleHandle Function](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulehandlea).

</dd> <dt>

*pResourceName* \[in\]
</dt> <dd>

Type: **[**LPCTSTR**](../winprog/windows-data-types.md)**

Name of the resource in hModule. If the compiler settings require Unicode, the data type LPCTSTR resolves to LPCWSTR. Otherwise, the data type resolves to LPCSTR.

</dd> <dt>

*pSrcFileName* \[in\]
</dt> <dd>

Type: **[**LPCTSTR**](../winprog/windows-data-types.md)**

Optional. Effect file name, which is used for error messages only. Can be **NULL**.

</dd> <dt>

*pDefines* \[in\]
</dt> <dd>

Type: **const [**D3D\_SHADER\_MACRO**](/windows/win32/api/d3dcommon/ns-d3dcommon-d3d_shader_macro)\***

A NULL-terminated array of shader macros (see [**D3D\_SHADER\_MACRO**](/windows/win32/api/d3dcommon/ns-d3dcommon-d3d_shader_macro)); set this to **NULL** to specify no macros.

</dd> <dt>

*pInclude* \[in\]
</dt> <dd>

Type: **[**ID3D10Include**](/previous-versions/windows/desktop/legacy/bb173775(v=vs.85))\***

A pointer to an include interface (see [**ID3D10Include Interface**](/previous-versions/windows/desktop/legacy/bb173775(v=vs.85))). This parameter can be **NULL**.

</dd> <dt>

*pProfile* \[in\]
</dt> <dd>

Type: **[**LPCSTR**](../winprog/windows-data-types.md)**

A string that specifies the [shader profile](../direct3dhlsl/dx-graphics-hlsl-models.md), or shader model.

</dd> <dt>

*HLSLFlags* \[in\]
</dt> <dd>

Type: **[**UINT**](../winprog/windows-data-types.md)**

HLSL compile options (see [D3D10\_SHADER Constants](d3d10-shader.md)).

</dd> <dt>

*FXFlags* \[in\]
</dt> <dd>

Type: **[**UINT**](../winprog/windows-data-types.md)**

Effect compile options (see [Compile and Effect Flags](d3d10-graphics-reference-effect-constants.md)).

</dd> <dt>

*pDevice* \[in\]
</dt> <dd>

Type: **[**ID3D10Device**](/windows/win32/api/D3D10/nn-d3d10-id3d10device)\***

A pointer to the device (see [**ID3D10Device Interface**](/windows/win32/api/D3D10/nn-d3d10-id3d10device)) that will use the resources.

</dd> <dt>

*pEffectPool* \[in\]
</dt> <dd>

Type: **[**ID3D10EffectPool**](/windows/win32/api/D3D10Effect/nn-d3d10effect-id3d10effectpool)\***

Pointer to an effect pool (see [**ID3D10EffectPool Interface**](/windows/win32/api/D3D10Effect/nn-d3d10effect-id3d10effectpool)) for sharing variables between effects.

</dd> <dt>

*pPump* \[in\]
</dt> <dd>

Type: **[**ID3DX10ThreadPump**](id3dx10threadpump.md)\***

A pointer to a thread pump interface (see [**ID3DX10ThreadPump Interface**](id3dx10threadpump.md)). Use **NULL** to specify that this function should not return until it is completed.

</dd> <dt>

*ppEffect* \[out\]
</dt> <dd>

Type: **[**ID3D10Effect**](/windows/win32/api/D3D10Effect/nn-d3d10effect-id3d10effect)\*\***

Address of a pointer to the effect (see [**ID3D10Effect Interface**](/windows/win32/api/D3D10Effect/nn-d3d10effect-id3d10effect)) that is created.

</dd> <dt>

*ppErrors* \[out\]
</dt> <dd>

Type: **[**ID3D10Blob**](/windows/win32/api/D3DCommon/nn-d3dcommon-id3d10blob)\*\***

The address of a pointer to memory (see [**ID3D10Blob Interface**](/windows/win32/api/D3DCommon/nn-d3dcommon-id3d10blob)) that contains effect compile errors, if there were any.

</dd> <dt>

*pHResult* \[out\]
</dt> <dd>

Type: **[**HRESULT**](https://msdn.microsoft.com/library/Bb401631(v=MSDN.10).aspx)\***

A pointer to the return value. May be **NULL**. If *pPump* is not **NULL**, then *pHResult* must be a valid memory location until the asynchronous execution completes.

</dd> </dl>

## Return value

Type: **[**HRESULT**](https://msdn.microsoft.com/library/Bb401631(v=MSDN.10).aspx)**

The return value is one of the values listed in [Direct3D 10 Return Codes](d3d10-graphics-reference-returnvalues.md).

## Requirements



|                   |                                                                                          |
|-------------------|------------------------------------------------------------------------------------------|
| Header<br/> | <dl> <dt>D3DX10Async.h</dt> </dl> |



## See also

<dl> <dt>

[General Purpose Functions](d3d10-graphics-reference-d3dx10-functions-general-purpose.md)
</dt> </dl>

 

 
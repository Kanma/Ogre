# List the header files
set (HEADER_FILES
  ${OGRE_SOURCE_DIR}/include/Ogre/asm_math.h
  ${OGRE_SOURCE_DIR}/include/Ogre/Ogre.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreAlignedAllocator.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreAnimable.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreAnimation.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreAnimationState.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreAnimationTrack.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreAny.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreArchive.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreArchiveFactory.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreArchiveManager.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreAtomicWrappers.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreAutoParamDataSource.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreAxisAlignedBox.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreBillboard.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreBillboardChain.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreBillboardParticleRenderer.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreBillboardSet.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreBitwise.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreBlendMode.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreBone.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreBorderPanelOverlayElement.h
  ${XMAKE_BINARY_DIR}/include/Ogre/OgreBuildSettings.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreCamera.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreCodec.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreColourValue.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreCommon.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreCompositionPass.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreCompositionTargetPass.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreCompositionTechnique.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreCompositor.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreCompositorChain.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreCompositorLogic.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreCompositorInstance.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreCompositorManager.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreConfig.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreConfigDialog.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreConfigFile.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreConfigOptionMap.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreController.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreControllerManager.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreConvexBody.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreCustomCompositionPass.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreDataStream.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreDDSCodec.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreDefaultHardwareBufferManager.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreDeflate.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreDepthBuffer.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreDistanceLodStrategy.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreDualQuaternion.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreDynLib.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreDynLibManager.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreEdgeListBuilder.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreEntity.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreErrorDialog.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreException.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreExternalTextureSource.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreExternalTextureSourceManager.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreFactoryObj.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreFileSystem.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreFont.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreFontManager.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreFrameListener.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreFreeImageCodec.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreFrustum.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreGpuProgram.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreGpuProgramManager.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreGpuProgramParams.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreGpuProgramUsage.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreHardwareBuffer.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreHardwareBufferManager.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreHardwareIndexBuffer.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreHardwareOcclusionQuery.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreHardwarePixelBuffer.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreHardwareVertexBuffer.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreHeaderPrefix.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreHeaderSuffix.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreHighLevelGpuProgram.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreHighLevelGpuProgramManager.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreImage.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreImageCodec.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreInstanceBatch.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreInstanceBatchHW.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreInstanceBatchHW_VTF.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreInstanceBatchShader.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreInstanceBatchVTF.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreInstanceManager.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreInstancedEntity.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreInstancedGeometry.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreIteratorRange.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreIteratorWrapper.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreIteratorWrappers.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreKeyFrame.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreLight.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreLodListener.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreLodStrategy.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreLodStrategyManager.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreLog.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreLogManager.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreManualObject.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreMaterial.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreMaterialManager.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreMaterialSerializer.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreMath.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreMatrix3.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreMatrix4.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreMemoryAllocatedObject.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreMemoryAllocatorConfig.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreMemoryNedAlloc.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreMemoryNedPooling.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreMemoryStdAlloc.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreMemorySTLAllocator.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreMemoryTracker.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreMesh.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreMeshFileFormat.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreMeshManager.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreMeshSerializer.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreMeshSerializerImpl.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreMovableObject.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreMovablePlane.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreNode.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreNumerics.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreOptimisedUtil.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreOverlay.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreOverlayContainer.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreOverlayElement.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreOverlayElementCommands.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreOverlayElementFactory.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreOverlayManager.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgrePanelOverlayElement.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreParticle.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreParticleAffector.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreParticleAffectorFactory.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreParticleEmitter.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreParticleEmitterCommands.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreParticleEmitterFactory.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreParticleIterator.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreParticleScriptCompiler.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreParticleSystem.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreParticleSystemManager.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreParticleSystemRenderer.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgrePass.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgrePatchMesh.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgrePatchSurface.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgrePixelCountLodStrategy.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgrePixelFormat.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgrePlane.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgrePlaneBoundedVolume.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgrePlatform.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgrePlatformInformation.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgrePlugin.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgrePolygon.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgrePose.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgrePredefinedControllers.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgrePrefabFactory.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgrePrerequisites.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreProfiler.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreProgressiveMesh.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgrePVRTCCodec.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreQuaternion.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreRadixSort.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreRay.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreRectangle.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreRectangle2D.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreRenderable.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreRenderObjectListener.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreRenderOperation.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreRenderQueue.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreRenderQueueInvocation.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreRenderQueueListener.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreRenderQueueSortingGrouping.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreRenderSystem.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreRenderSystemCapabilities.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreRenderSystemCapabilitiesManager.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreRenderSystemCapabilitiesSerializer.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreRenderTarget.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreRenderTargetListener.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreRenderTexture.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreRenderToVertexBuffer.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreRenderWindow.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreResource.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreResourceBackgroundQueue.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreResourceGroupManager.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreResourceManager.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreRibbonTrail.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreRoot.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreRotationalSpline.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreSceneManager.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreSceneManagerEnumerator.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreSceneNode.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreSceneQuery.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreScriptCompiler.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreScriptLexer.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreScriptLoader.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreScriptParser.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreScriptTranslator.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreSearchOps.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreSerializer.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreShadowCameraSetup.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreShadowCameraSetupFocused.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreShadowCameraSetupLiSPSM.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreShadowCameraSetupPlaneOptimal.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreShadowCameraSetupPSSM.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreShadowCaster.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreShadowTextureManager.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreShadowVolumeExtrudeProgram.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreSharedPtr.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreSimpleRenderable.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreSimpleSpline.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreSingleton.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreSkeleton.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreSkeletonFileFormat.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreSkeletonInstance.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreSkeletonManager.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreSkeletonSerializer.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreSmallVector.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreSphere.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreSpotShadowFadePng.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreStableHeaders.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreStaticFaceGroup.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreStaticGeometry.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreStdHeaders.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreStreamSerialiser.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreString.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreStringConverter.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreStringInterface.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreStringSerialiser.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreStringVector.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreSubEntity.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreSubMesh.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreTagPoint.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreTangentSpaceCalc.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreTechnique.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreTextAreaOverlayElement.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreTexture.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreTextureManager.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreTextureUnitState.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreTimer.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreUnifiedHighLevelGpuProgram.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreUserObjectBindings.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreUTFString.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreVector2.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreVector3.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreVector4.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreVertexBoneAssignment.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreVertexIndexData.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreViewport.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreWindowEventUtilities.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreWireBoundingBox.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreWorkQueue.h
  ${OGRE_SOURCE_DIR}/include/Ogre/OgreZip.h
)


# List the source files
set (SOURCE_FILES
  OgreAlignedAllocator.cpp
  OgreAnimable.cpp
  OgreAnimation.cpp
  OgreAnimationState.cpp
  OgreAnimationTrack.cpp
  OgreArchiveManager.cpp
  OgreAutoParamDataSource.cpp
  OgreAxisAlignedBox.cpp
  OgreBillboard.cpp
  OgreBillboardChain.cpp
  OgreBillboardParticleRenderer.cpp
  OgreBillboardSet.cpp
  OgreBone.cpp
  OgreBorderPanelOverlayElement.cpp
  OgreCamera.cpp
  OgreCodec.cpp
  OgreColourValue.cpp
  OgreCommon.cpp
  OgreCompositionPass.cpp
  OgreCompositionTargetPass.cpp
  OgreCompositionTechnique.cpp
  OgreCompositor.cpp
  OgreCompositorChain.cpp
  OgreCompositorInstance.cpp
  OgreCompositorManager.cpp
  OgreConfigFile.cpp
  OgreControllerManager.cpp
  OgreConvexBody.cpp
  OgreDataStream.cpp
  OgreDDSCodec.cpp
  OgreDefaultHardwareBufferManager.cpp
  OgreDefaultSceneQueries.cpp
  OgreDeflate.cpp
  OgreDepthBuffer.cpp
  OgreDistanceLodStrategy.cpp
  OgreDualQuaternion.cpp
  OgreDynLib.cpp
  OgreDynLibManager.cpp
  OgreEdgeListBuilder.cpp
  OgreEntity.cpp
  OgreException.cpp
  OgreExternalTextureSource.cpp
  OgreExternalTextureSourceManager.cpp
  OgreFileSystem.cpp
  OgreFont.cpp
  OgreFontManager.cpp
  OgreFreeImageCodec.cpp
  OgreFrustum.cpp
  OgreGpuProgram.cpp
  OgreGpuProgramManager.cpp
  OgreGpuProgramParams.cpp
  OgreGpuProgramUsage.cpp
  OgreHardwareBufferManager.cpp
  OgreHardwareIndexBuffer.cpp
  OgreHardwareOcclusionQuery.cpp
  OgreHardwarePixelBuffer.cpp
  OgreHardwareVertexBuffer.cpp
  OgreHighLevelGpuProgram.cpp
  OgreHighLevelGpuProgramManager.cpp
  OgreImage.cpp
  OgreImageResampler.h
  OgreInstanceBatch.cpp
  OgreInstanceBatchHW.cpp
  OgreInstanceBatchHW_VTF.cpp
  OgreInstanceBatchShader.cpp
  OgreInstanceBatchVTF.cpp
  OgreInstanceManager.cpp
  OgreInstancedEntity.cpp
  OgreInstancedGeometry.cpp
  OgreKeyFrame.cpp
  OgreLight.cpp
  OgreLodStrategy.cpp
  OgreLodStrategyManager.cpp
  OgreLog.cpp
  OgreLogManager.cpp
  ogremain.map
  OgreManualObject.cpp
  OgreMaterial.cpp
  OgreMaterialManager.cpp
  OgreMaterialSerializer.cpp
  OgreMath.cpp
  OgreMatrix3.cpp
  OgreMatrix4.cpp
  OgreMemoryAllocatedObject.cpp
  OgreMemoryNedAlloc.cpp
  OgreMemoryNedPooling.cpp
  OgreMemoryTracker.cpp
  OgreMesh.cpp
  OgreMeshManager.cpp
  OgreMeshSerializer.cpp
  OgreMeshSerializerImpl.cpp
  OgreMovableObject.cpp
  OgreMovablePlane.cpp
  OgreNode.cpp
  OgreNumerics.cpp
  OgreOptimisedUtil.cpp
  OgreOptimisedUtilGeneral.cpp
#  OgreOptimisedUtilNEON.cpp
  OgreOptimisedUtilSSE.cpp
#  OgreOptimisedUtilVFP.cpp
  OgreOverlay.cpp
  OgreOverlayContainer.cpp
  OgreOverlayElement.cpp
  OgreOverlayElementCommands.cpp
  OgreOverlayElementFactory.cpp
  OgreOverlayManager.cpp
  OgrePanelOverlayElement.cpp
  OgreParticle.cpp
  OgreParticleEmitter.cpp
  OgreParticleEmitterCommands.cpp
  OgreParticleIterator.cpp
  OgreParticleSystem.cpp
  OgreParticleSystemManager.cpp
  OgrePass.cpp
  OgrePatchMesh.cpp
  OgrePatchSurface.cpp
  OgrePixelCountLodStrategy.cpp
  OgrePixelConversions.h
  OgrePixelFormat.cpp
  OgrePlane.cpp
  OgrePlatformInformation.cpp
  OgrePolygon.cpp
  OgrePose.cpp
  OgrePrecompiledHeaders.cpp
  OgrePredefinedControllers.cpp
  OgrePrefabFactory.cpp
  OgreProfiler.cpp
  OgreProgressiveMesh.cpp
  OgrePVRTCCodec.cpp
  OgreQuaternion.cpp
  OgreRectangle2D.cpp
  OgreRenderQueue.cpp
  OgreRenderQueueInvocation.cpp
  OgreRenderQueueSortingGrouping.cpp
  OgreRenderSystem.cpp
  OgreRenderSystemCapabilities.cpp
  OgreRenderSystemCapabilitiesManager.cpp
  OgreRenderSystemCapabilitiesSerializer.cpp
  OgreRenderTarget.cpp
  OgreRenderTexture.cpp
  OgreRenderToVertexBuffer.cpp
  OgreRenderWindow.cpp
  OgreResource.cpp
  OgreResourceBackgroundQueue.cpp
  OgreResourceGroupManager.cpp
  OgreResourceManager.cpp
  OgreRibbonTrail.cpp
  OgreRoot.cpp
  OgreRotationSpline.cpp
  OgreSceneManager.cpp
  OgreSceneManagerEnumerator.cpp
  OgreSceneNode.cpp
  OgreSceneQuery.cpp
  OgreScriptCompiler.cpp
  OgreScriptLexer.cpp
  OgreScriptParser.cpp
  OgreScriptTranslator.cpp
  OgreSerializer.cpp
  OgreShadowCameraSetup.cpp
  OgreShadowCameraSetupFocused.cpp
  OgreShadowCameraSetupLiSPSM.cpp
  OgreShadowCameraSetupPlaneOptimal.cpp
  OgreShadowCameraSetupPSSM.cpp
  OgreShadowCaster.cpp
  OgreShadowTextureManager.cpp
  OgreShadowVolumeExtrudeProgram.cpp
  OgreSIMDHelper.h
  OgreSimpleRenderable.cpp
  OgreSimpleSpline.cpp
  OgreSkeleton.cpp
  OgreSkeletonInstance.cpp
  OgreSkeletonManager.cpp
  OgreSkeletonSerializer.cpp
  OgreSmallVector.cpp
  OgreStaticGeometry.cpp
  OgreStreamSerialiser.cpp
  OgreString.cpp
  OgreStringConverter.cpp
  OgreStringInterface.cpp
  OgreStringSerialiser.cpp
  OgreSubEntity.cpp
  OgreSubMesh.cpp
  OgreTagPoint.cpp
  OgreTangentSpaceCalc.cpp
  OgreTechnique.cpp
  OgreTextAreaOverlayElement.cpp
  OgreTexture.cpp
  OgreTextureManager.cpp
  OgreTextureUnitState.cpp
  OgreUnifiedHighLevelGpuProgram.cpp
  OgreUserObjectBindings.cpp
  OgreUTFString.cpp
  OgreVector2.cpp
  OgreVector3.cpp
  OgreVector4.cpp
  OgreVertexIndexData.cpp
  OgreViewport.cpp
  OgreWindowEventUtilities.cpp
  OgreWireBoundingBox.cpp
  OgreWorkQueue.cpp
  OgreZip.cpp
)

# Add platform specific files
if (WIN32)

  include_directories("include/WIN32")

  set(PLATFORM_HEADER_FILES
    ${OGRE_SOURCE_DIR}/include/Ogre/WIN32/OgreConfigDialogImp.h
    ${OGRE_SOURCE_DIR}/include/Ogre/WIN32/OgreErrorDialogImp.h
    ${OGRE_SOURCE_DIR}/include/Ogre/WIN32/OgreTimerImp.h
  )

  set(PLATFORM_SOURCE_FILES
    WIN32/resource.h
    WIN32/OgreConfigDialog.cpp
    WIN32/OgreErrorDialog.cpp
    WIN32/OgreTimer.cpp
    WIN32/OgreWin32Resources.rc
    WIN32/winres.h
  )  

  set(RESOURCE_FILES
    WIN32/resource.h
    WIN32/OgreWin32Resources.rc
    WIN32/winres.h
  )

  source_group(Resources FILES ${RESOURCE_FILES})

elseif (APPLE)

    include_directories("${OGRE_SOURCE_DIR}/include/Ogre/OSX")

    set(PLATFORM_HEADER_FILES
      ${OGRE_SOURCE_DIR}/include/Ogre/OSX/macUtils.h
      ${OGRE_SOURCE_DIR}/include/Ogre/OSX/OgreConfigDialogImp.h
      ${OGRE_SOURCE_DIR}/include/Ogre/OSX/OgreErrorDialogImp.h
      ${OGRE_SOURCE_DIR}/include/Ogre/OSX/OgreTimerImp.h
    )

    set(PLATFORM_SOURCE_FILES
      OSX/OgreConfigDialog.mm
      OSX/OgreErrorDialog.mm
      OSX/OgreTimer.cpp
      OSX/macUtils.cpp
      OgreSearchOps.cpp
      ${OGRE_SOURCE_DIR}/include/Ogre/OSX/ogrelogo.png
    )

    set(RESOURCE_FILES
        ${OGRE_SOURCE_DIR}/include/Ogre/OSX/ogrelogo.png
    )

    source_group(Resources FILES ${RESOURCE_FILES})

    set(PLATFORM_LIBS "-framework Cocoa" "-framework Carbon")

elseif (UNIX)

  include_directories(${OGRE_SOURCE_DIR}/include/Ogre/GLX ${X11_INCLUDE_DIR})

  set(PLATFORM_HEADER_FILES
      ${OGRE_SOURCE_DIR}/include/Ogre/GLX/OgreConfigDialogImp.h
      ${OGRE_SOURCE_DIR}/include/Ogre/GLX/OgreErrorDialogImp.h
      ${OGRE_SOURCE_DIR}/include/Ogre/GLX/OgreTimerImp.h
  )
  
  set(PLATFORM_SOURCE_FILES
    GLX/GLX_backdrop.h
    GLX/OgreConfigDialog.cpp
    GLX/OgreErrorDialog.cpp
    GLX/OgreTimer.cpp
    OgreSearchOps.cpp
  )
  
  set(PLATFORM_LIBS ${X11_LIBRARIES} ${X11_Xt_LIB} ${XAW_LIBRARY} pthread dl)

endif ()


# Configure threading files
set(THREAD_HEADER_FILES
    ${OGRE_SOURCE_DIR}/include/Ogre/Threading/OgreThreadDefines.h
    ${OGRE_SOURCE_DIR}/include/Ogre/Threading/OgreThreadHeaders.h
    ${OGRE_SOURCE_DIR}/include/Ogre/Threading/OgreDefaultWorkQueue.h
)

if (OGRE_THREAD_PROVIDER EQUAL 0)
    
    list(APPEND THREAD_HEADER_FILES
        ${OGRE_SOURCE_DIR}/include/Ogre/Threading/OgreThreadDefinesNone.h
        ${OGRE_SOURCE_DIR}/include/Ogre/Threading/OgreDefaultWorkQueueStandard.h
    )
    
    set(THREAD_SOURCE_FILES
        Threading/OgreDefaultWorkQueueStandard.cpp
    )
    
elseif (OGRE_THREAD_PROVIDER EQUAL 1)
    
    list(APPEND THREAD_HEADER_FILES
        ${OGRE_SOURCE_DIR}/include/Ogre/Threading/OgreThreadDefinesBoost.h
        ${OGRE_SOURCE_DIR}/include/Ogre/Threading/OgreThreadHeadersBoost.h
        ${OGRE_SOURCE_DIR}/include/Ogre/Threading/OgreDefaultWorkQueueStandard.h
    )
    
    set(THREAD_SOURCE_FILES
        Threading/OgreDefaultWorkQueueStandard.cpp
    )

endif ()


# Generate the header containing the configuration
configure_file(${OGRE_SOURCE_DIR}/include/Ogre/OgreBuildSettings.h.in
               ${XMAKE_BINARY_DIR}/include/Ogre/OgreBuildSettings.h)


# Add needed definitions and nedmalloc include dir
add_definitions(-DOGRE_NONCLIENT_BUILD -D_MT -D_USRDLL)
include_directories(
    ${OGRE_SOURCE_DIR}/include/Ogre
    ${XMAKE_BINARY_DIR}/include/Ogre
    ${CMAKE_CURRENT_SOURCE_DIR}/nedmalloc)


xmake_import_search_paths(FREEIMAGE)
xmake_import_search_paths(FREETYPE)
xmake_import_search_paths(ZLIB)
xmake_import_search_paths(ZZIPLIB)


# Declaration of the library
if (APPLE)
    xmake_create_framework(OGRE Ogre ${OGRE_VERSION} ${OGRE_VERSION_MAJOR} ${HEADER_FILES} ${SOURCE_FILES} ${PLATFORM_HEADER_FILES} ${PLATFORM_SOURCE_FILES} ${THREAD_HEADER_FILES} ${THREAD_SOURCE_FILES})
else()
    xmake_create_dynamic_library(OGRE Ogre ${OGRE_VERSION} ${OGRE_VERSION_MAJOR} ${HEADER_FILES} ${SOURCE_FILES} ${PLATFORM_HEADER_FILES} ${PLATFORM_SOURCE_FILES} ${THREAD_HEADER_FILES} ${THREAD_SOURCE_FILES})
endif()

if (UNIX AND NOT APPLE)
    xmake_add_to_property(OGRE COMPILE_FLAGS "-msse")
endif()

if (WIN32)
    xmake_add_to_property(OGRE LINK_FLAGS "/INCREMENTAL:NO")
endif()

xmake_disable_vs_warning(OGRE 4305 NO)

xmake_project_link(OGRE FREEIMAGE FREETYPE ZZIPLIB)
target_link_libraries(Ogre ${PLATFORM_LIBS})

if (OGRE_THREAD_SUPPORT)
    target_link_libraries(Ogre ${OGRE_THREAD_LIBRARIES})
endif ()


# MacOS X Framework stuff
if (APPLE)
    set(COCOAVIEW_HEADERS ${OGRE_SOURCE_DIR}/RenderSystems/GL/include/OSX/OgreOSXCocoaView.h)

    set_target_properties(Ogre PROPERTIES PUBLIC_HEADER "${HEADER_FILES}")

    add_custom_command(TARGET Ogre POST_BUILD
      COMMAND mkdir ARGS -p ${XMAKE_BINARY_DIR}/bin/Ogre.framework/Versions/${OGRE_VERSION}/Headers/Threading
      COMMAND cp ARGS ${THREAD_HEADER_FILES} ${XMAKE_BINARY_DIR}/bin/Ogre.framework/Versions/${OGRE_VERSION}/Headers/Threading
      COMMAND mkdir ARGS -p ${XMAKE_BINARY_DIR}/bin/Ogre.framework/Versions/${OGRE_VERSION}/Headers/OSX
      COMMAND cp ARGS ${PLATFORM_HEADER_FILES} ${XMAKE_BINARY_DIR}/bin/Ogre.framework/Versions/${OGRE_VERSION}/Headers/OSX/
      COMMAND cp ARGS ${COCOAVIEW_HEADERS} ${XMAKE_BINARY_DIR}/bin/Ogre.framework/Versions/${OGRE_VERSION}/Headers/OSX/
    )

    set_target_properties(Ogre PROPERTIES RESOURCE "${RESOURCE_FILES}")
    set_source_files_properties("${RESOURCE_FILES}" PROPERTIES MACOSX_PACKAGE_LOCATION Resources)
endif ()


# Exportations
xmake_export_include_paths(OGRE ${OGRE_SOURCE_DIR}/include
                                ${XMAKE_BINARY_DIR}/include
                                ${XMAKE_BINARY_DIR}/include/Ogre)

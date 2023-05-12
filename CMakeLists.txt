project(bmalloc)

set(CMAKE_CXX_STANDARD 17)

include_directories(
	bmalloc
	bmalloc/darwin
)

add_darling_static_library(bmalloc FAT
	SOURCES
		bmalloc/AllIsoHeaps.cpp
		bmalloc/Allocator.cpp
		bmalloc/AvailableMemory.cpp
		bmalloc/Cache.cpp
		bmalloc/CryptoRandom.cpp
		bmalloc/Deallocator.cpp
		bmalloc/DebugHeap.cpp
		bmalloc/Environment.cpp
		bmalloc/FreeList.cpp
		bmalloc/Gigacage.cpp
		bmalloc/Heap.cpp
		bmalloc/HeapConstants.cpp
		bmalloc/HeapKind.cpp
		bmalloc/IsoHeapImpl.cpp
		bmalloc/IsoPage.cpp
		bmalloc/IsoSharedHeap.cpp
		bmalloc/IsoSharedPage.cpp
		bmalloc/IsoTLS.cpp
		bmalloc/IsoTLSEntry.cpp
		bmalloc/IsoTLSLayout.cpp
		bmalloc/LargeMap.cpp
		bmalloc/Logging.cpp
		bmalloc/Mutex.cpp
		bmalloc/ObjectType.cpp
		bmalloc/ObjectTypeTable.cpp
		bmalloc/PerProcess.cpp
		bmalloc/ProcessCheck.mm
		bmalloc/Scavenger.cpp
		bmalloc/Zone.cpp
		bmalloc/bmalloc.cpp
)

add_darling_library(mbmalloc
	bmalloc/mbmalloc.cpp
)
make_fat(mbmalloc)

target_link_libraries(mbmalloc
	system
	cxx
	objc
	Foundation

	bmalloc
)

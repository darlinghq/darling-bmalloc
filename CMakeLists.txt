project(bmalloc)

add_darling_static_library(bmalloc FAT
	SOURCES
		bmalloc/Allocator.cpp
		bmalloc/Cache.cpp
		bmalloc/Deallocator.cpp
		bmalloc/Environment.cpp
		bmalloc/Heap.cpp
		bmalloc/LargeMap.cpp
		bmalloc/Logging.cpp
		bmalloc/ObjectType.cpp
		bmalloc/StaticMutex.cpp
		bmalloc/VMHeap.cpp
		bmalloc/Zone.cpp
)

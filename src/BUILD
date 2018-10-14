package_group(
  name = "ssocketio",
  packages = [
    "//src/...",
    "//src/internal/...",
  ]
)

package(default_visibility = ["//src:ssocketio"])

cc_library(
  name = "ssio_client",
  visibility = ["//visibility:public"],
  srcs = [
    "ssio_client.cpp",
		"ssio_socket.cpp",
  ],
  deps = [
	  ":ssio_client_h",
		":ssio_message_h",
		":ssio_socket_h",
    "//src/internal:ssio_client_impl",
		"//src/internal:ssio_packet",
  ],
	linkopts = [
    "-lrt",
    "-lcrypto",
    "-lssl",
    "-lz",
  ],
	alwayslink = 1,
)

cc_library(
  name = "ssio_tls_client",
  visibility = ["//visibility:public"],
  srcs = [
    "ssio_client.cpp",
		"ssio_socket.cpp",
  ],
  deps = [
	  ":ssio_client_h",
		":ssio_message_h",
		":ssio_socket_h",
    "//src/internal:ssio_tls_client_impl",
		"//src/internal:ssio_packet",
  ],
	linkopts = [
    "-lrt",
    "-lcrypto",
    "-lssl",
    "-lz",
  ],
	alwayslink = 1,
)

cc_library(
  name = "ssio_client_h",
	hdrs = ["ssio_client.h"],
	deps = [
	  ":ssio_message_h",
		":ssio_socket_h",
	]
)

cc_library(
  name = "ssio_message_h",
	hdrs = ["ssio_message.h"],
)

cc_library(
  name = "ssio_socket_h",
	hdrs = ["ssio_socket.h"],
	deps = [
	  ":ssio_message_h",
	]
)
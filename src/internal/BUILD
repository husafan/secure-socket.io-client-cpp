package(default_visibility = ["//src:ssocketio"])

config_setting(
	name = "logging_enabled",
	values = {
	  "compilation_mode": "dbg",
	},
)

cc_library(
  name = "ssio_client_impl",
  hdrs = ["ssio_client_impl.h"],
  srcs = ["ssio_client_impl.cpp"],
	copts = select({
	  ":logging_enabled": ["-DDEBUG"],
		"//conditions:default": [],
	}),
  deps = [
    ":ssio_packet",
		"//src:ssio_client_h",
    "@boost//:asio",
    "@boost//:version",
    "@websocketpp//:websocketpp"
  ]
)

cc_library(
  name = "ssio_tls_client_impl",
  hdrs = ["ssio_client_impl.h"],
  srcs = ["ssio_client_impl.cpp"],
	copts = select({
	  ":logging_enabled": ["-DDEBUG"],
		"//conditions:default": [],
	}) + [
	  "-DSIO_TLS",
	],
  deps = [
    ":ssio_packet",
		"//src:ssio_client_h",
    "@boost//:asio",
    "@boost//:version",
    "@websocketpp//:websocketpp"
  ]
)

cc_library(
  name = "ssio_packet",
  hdrs = ["ssio_packet.h"],
  srcs = ["ssio_packet.cpp"],
  deps = [
    "//src:ssio_message_h",
    "@boost//:lexical_cast",
    "@rapidjson//:rapidjson",
  ]
)
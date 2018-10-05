package(default_visibility = ["//src:ssocketio"])

cc_library(
  name = "ssio_client_impl",
  hdrs = ["ssio_client_impl.h"],
  srcs = ["ssio_client_impl.cpp"],
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
set(srcs "")
set(include_dirs "")

list(APPEND srcs "src/api/api.c"

                 "src/collections/bytes.c"
                 "src/collections/intmap.c"
                 "src/collections/list.c"
                 "src/collections/string.c"
                 "src/collections/vec.c"

                 "src/link/config/bt.c"
                 "src/link/config/serial.c"
                 "src/link/config/tcp.c"
                 "src/link/config/udp.c"
                 "src/link/config/ws.c"
                 "src/link/multicast/bt.c"
                 "src/link/multicast/udp.c"
                 "src/link/unicast/serial.c"
                 "src/link/unicast/tcp.c"
                 "src/link/unicast/udp.c"
                 "src/link/unicast/ws.c"
                 "src/link/endpoint.c"
                 "src/link/link.c"

                 "src/net/config.c"
                 "src/net/logger.c"
                 "src/net/memory.c"
                 "src/net/primitives.c"
                 "src/net/publish.c"
                 "src/net/query.c"
                 "src/net/resource.c"
                 "src/net/session.c"
                 "src/net/subscribe.c"

                 "src/protocol/codec.c"
                 "src/protocol/config.c"
                 "src/protocol/iobuf.c"
                 "src/protocol/keyexpr.c"
                 "src/protocol/msg.c"
                 "src/protocol/msgcodec.c"

                 "src/session/query.c"
                 "src/session/queryable.c"
                 "src/session/resource.c"
                 "src/session/rx.c"
                 "src/session/scout.c"
                 "src/session/subscription.c"
                 "src/session/tx.c"
                 "src/session/utils.c"

                 "src/system/espidf/network.c"
                 "src/system/espidf/system.c"

                 "src/transport/common/join.c"
                 "src/transport/common/lease.c"
                 "src/transport/common/read.c"
                 "src/transport/common/rx.c"
                 "src/transport/common/tx.c"
                 "src/transport/multicast/link/task/join.c"
                 "src/transport/multicast/link/task/lease.c"
                 "src/transport/multicast/link/task/read.c"
                 "src/transport/multicast/link/rx.c"
                 "src/transport/multicast/link/tx.c"
                 "src/transport/unicast/link/task/lease.c"
                 "src/transport/unicast/link/task/read.c"
                 "src/transport/unicast/link/rx.c"
                 "src/transport/unicast/link/tx.c"
                 "src/transport/manager.c"
                 "src/transport/peer_entry.c"
                 "src/transport/transport.c"
                 "src/transport/utils.c"

                 "src/utils/checksum.c"
                 "src/utils/encoding.c"
                 "src/utils/pointers.c"
                 "src/utils/string.c")

list(APPEND include_dirs "include"
                         "include/zenoh-pico"
                         "include/zenoh-pico/api"
                         "include/zenoh-pico/collections"
                         "include/zenoh-pico/link"
                         "include/zenoh-pico/link/config"
                         "include/zenoh-pico/protocol"
                         "include/zenoh-pico/session"
                         "include/zenoh-pico/system"
                         "include/zenoh-pico/system/link"
                         "include/zenoh-pico/transport")

idf_component_register(SRCS "${srcs}"
                       INCLUDE_DIRS "${include_dirs}"
                       REQUIRES driver)

target_compile_definitions(${COMPONENT_LIB} PRIVATE ZENOH_ESPIDF=1)



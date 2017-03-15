FROM mkeith/ark:latest
LABEL org.freenas.interactive="false"                                     \
      org.freenas.version="1"                                             \
      org.freenas.upgradeable="true"                                      \
      org.freenas.expose-ports-at-host="true"                             \
      org.freenas.autostart="true"                                        \
      org.freenas.web-ui-protocol="http"                                  \
      org.freenas.web-ui-port=""                                          \
      org.freenas.web-ui-path=""                                          \
      org.freenas.port-mappings="7778:7778/udp,27015:27015/udp,27020/udp" \
      org.freenas.volumes="[						                      \
          {								                                  \
              \"name\": \"/server\",					                  \
              \"descr\": \"ARK Server Installation Volume\"	              \
          }								                                  \
      ]"                                                                  \
      org.freenas.settings="[ 				                              \
          {								                                  \
              \"env\": \"PUID\",			                              \
              \"descr\": \"ARK USER ID\",                                 \
              \"optional\": true			                              \
          },								                              \
          {								                                  \
              \"env\": \"PGID\",			                              \
              \"descr\": \"ARK GROUP ID\",                                \
              \"optional\": true			                              \
          },                                                              \
          {								                                  \
              \"env\": \"SERVER_NAME\",			                          \
              \"descr\": \"SERVER NAME\",                                 \
              \"optional\": true			                              \
          },                                                              \
          {								                                  \
              \"env\": \"SERVER_PASSWORD\",			                      \
              \"descr\": \"SERVER PASSWORD\",                             \
              \"optional\": true			                              \
          },                                                              \
          {								                                  \
              \"env\": \"SERVER_ADMIN_PASSWORD\",			              \
              \"descr\": \"SERVER ADMIN PASSWORD\",                       \
              \"optional\": true			                              \
          },                                                              \
      ]"                                                                  \
      org.freenas.static-volumes="[				                          \
          {								                                  \
              \"container_path\": \"/dev/rtc\",	                          \
              \"host_path\": \"/dev/rtc\",		                          \
              \"readonly\": \"true\"			                          \
          }								                                  \
      ]"
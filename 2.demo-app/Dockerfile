# Use busybox as the base image
FROM busybox

# Add shell script
RUN echo -e '#!/bin/sh\nwhile true\ndo\necho Hello, world!\nsleep 5\ndone' > /hello.sh

# Make script executable
RUN chmod +x /hello.sh

# Run the script
CMD ["/hello.sh"]
# Copyright 2022 The OWASP Coraza contributors
# SPDX-License-Identifier: Apache-2.0

FROM ghcr.io/coreruleset/go-ftw:0.4.9

RUN apk update && apk add curl

WORKDIR /workspace

# TODO update when new CRS version is tagged: https://github.com/coreruleset/coreruleset/archive/refs/tags/v4.0.0-rc1.tar.gz
ADD https://github.com/coreruleset/coreruleset/tarball/477d8c3431d042294af2651f08d63d10b6f3fd60 /workspace/coreruleset/
RUN cd coreruleset && tar -xf 477d8c3431d042294af2651f08d63d10b6f3fd60 --strip-components 1

COPY ftw.yml /workspace/ftw.yml
COPY tests.sh /workspace/tests.sh

ENTRYPOINT ["sh"]
CMD ["-c", "/workspace/tests.sh"]


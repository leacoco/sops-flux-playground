# Generate the gpg key

gpg --batch --full-generate-key <<EOF
Key-Type: 1
Key-Length: 4096
Subkey-Type: 1
Name-Real: prod-cluster
Name-Email: leacoco@softcomweb.info
Exxpire-Date: 0
%no-protection
EOF
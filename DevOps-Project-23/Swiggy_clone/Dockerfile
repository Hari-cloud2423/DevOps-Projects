# ---------- BUILD STAGE ----------
FROM public.ecr.aws/docker/library/node:16 AS builder

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .
RUN npm run build


# ---------- PRODUCTION STAGE ----------
FROM public.ecr.aws/docker/library/node:16

WORKDIR /app

# install serve package
RUN npm install -g serve

# copy build files
COPY --from=builder /app/build ./build

# expose port 3000
EXPOSE 3000

# run production server
CMD ["serve", "-s", "build", "-l", "3000"]

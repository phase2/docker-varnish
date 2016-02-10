![logo](https://www.phase2technology.com/wp-content/uploads/2015/06/logo-retina.png)

# Varnish

Varnish 4 container with a confd template that outputs a nice Drupal-compatible VCL

## Configuration

### Environment Variables

#### VARNISH_BACKEND_HOST

The hostname that Varnish uses for its backend. It defaults to 'www'.

In a Dockerfile:
```
ENV VARNISH_BACKEND_HOST www
```

Via Docker Compose file:
```
environment:
  VARNISH_BACKEND_HOST: www
```

#### VARNISH_BACKEND_PORT

The port to which Varnish connects to for its backend. It defaults to '80'.


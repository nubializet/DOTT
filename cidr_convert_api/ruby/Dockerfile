FROM ruby:2-alpine

WORKDIR /app

COPY ./cidr_convert_api/Gemfile .
RUN gem install bundler \
    && bundle install

COPY ./cidr_convert_api .
CMD ["ash", "-c", "ruby api.rb"]
# docker build -t rbm .
# docker run -ti -p 8000:8000 rbm

require './app'

guard 'sprockets2', :sprockets => App.sprockets, :digest => false do
  watch(%r{^assets/.+$})
  watch('app.rb')
end

spec_location = "spec/%s_spec"
guard 'jasmine-headless-webkit' do
  watch(%r{^src/(.*)\.(coffee|js)$}) { |m| newest_js_file(spec_location % m[1]) }
  watch(%r{^spec/helpers*})
  watch(%r{^spec/(.*)_spec\..*}) { |m| newest_js_file(spec_location % m[1]) }
end

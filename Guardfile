
PROJECT = Pathname.new(Dir.pwd).basename

guard :shell do
  watch(/.*\.cabal$/) do
    system %{cabal configure --enable-tests}
    puts "Configured"
  end
end

guard :shell do
  watch(/.*.l?hs$/) do
    system %{cabal build && ./dist/build/#{PROJECT}-specs/#{PROJECT}-specs}
  end
end

